
### gRPC?

```

{
  "created":"@1711241045.247364900",
  "description":"Protocol not available",
  "errno":92,
  "file":"external/com_github_grpc_grpc/src/core/lib/iomgr/socket_utils_common_posix.cc",
  "file_line":202,
  "os_error":"Protocol not available",
  "syscall":"getsockopt(SO_REUSEPORT)"
}

```

### config?

Config (path: /home/pi/workspace/fm/TradeMaster/configs/algorithmic_trading/algorithmic_trading_FX_deepscalper_deepscalper_adam_mse.py):
{
  "data":{
    "type":"AlgorithmicTradingDataset",
    "data_path":"data/algorithmic_trading/FX",
    "train_path":"data/algorithmic_trading/FX/train.csv",
    "valid_path":"data/algorithmic_trading/FX/valid.csv",
    "test_path":"data/algorithmic_trading/FX/test.csv",
    "test_dynamic_path":"data/algorithmic_trading/FX/Market_Dynamics_Model/YUAN/test_labeled_slice_and_merge_model_3dynamics_minlength12_quantile_labeling.csv",
    "tech_indicator_list":[
      "high",
      "low",
      "open",
      "close",
      "adjcp",
      "zopen",
      "zhigh",
      "zlow",
      "zadjcp",
      "zclose",
      "zd_5",
      "zd_10",
      "zd_15",
      "zd_20",
      "zd_25",
      "zd_30"
    ],
    "backward_num_day":5,
    "forward_num_day":5,
    "test_dynamic":"-1"
  },
  "environment":{
    "type":"AlgorithmicTradingEnvironment"
  },
  "agent":{
    "type":"AlgorithmicTradingDQN",
    "max_step":12345,
    "reward_scale":1,
    "repeat_times":1,
    "gamma":0.9,
    "batch_size":64,
    "clip_grad_norm":3.0,
    "soft_update_tau":0,
    "state_value_tau":0.005
  },
  "trainer":{
    "type":"AlgorithmicTradingTrainer",
    "epochs":20,
    "work_dir":"work_dir/algorithmic_trading_FX_deepscalper_deepscalper_adam_mse",
    "seeds_list":[
      12345
    ],
    "batch_size":64,
    "horizon_len":128,
    "buffer_size":1000000.0,
    "num_threads":8,
    "if_remove":false,
    "if_discrete":true,
    "if_off_policy":true,
    "if_keep_save":true,
    "if_over_write":false,
    "if_save_buffer":false
  },
  "loss":{
    "type":"MSELoss"
  },
  "optimizer":{
    "type":"Adam",
    "lr":0.001
  },
  "act":{
    "type":"QNet",
    "state_dim":82,
    "action_dim":3,
    "dims":[
      64,
      32
    ],
    "explore_rate":0.25
  },
  "cri":"None",
  "transition":{
    "type":"Transition"
  },
  "task_name":"algorithmic_trading",
  "dataset_name":"FX",
  "optimizer_name":"adam",
  "loss_name":"mse",
  "net_name":"deepscalper",
  "agent_name":"deepscalper",
  "work_dir":"work_dir/algorithmic_trading_FX_deepscalper_deepscalper_adam_mse",
  "batch_size":64
}

```
