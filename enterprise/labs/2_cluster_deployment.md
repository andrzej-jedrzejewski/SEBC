```json
curl -u andrzej-jedrzejewski:cloudera 'http://localhost:7180/api/v2/cm/deployment'
{
  "timestamp" : "2017-03-08T11:20:33.819Z",
  "clusters" : [ {
    "name" : "andrzej-jedrzejewski",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "895483904"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "895483904"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "4402079334"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "740"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-10-0-0-206.eu-west-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "ankara123"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-4e19ee9c588f9e21ccccf396da941aea",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0e34aa518703179bc"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-6c0aa4e806a45f633cf826db6cf95d65",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-001ab783b0a5c737a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-749903ca081507f374b03e68c4b104cf",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0c2cf40e7ebd7d2c5"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-ab7d0cd195c8b21e52fd73bcd6ad3f6a",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0c270163f9e432235"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-af0aae7bccb740a539c0725d23bda135",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-01d1fca973a4a682a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-6c0aa4e806a45f633cf826db6cf95d65",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-001ab783b0a5c737a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a0klb429h3sxk6bhe18dw7e8h"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-6c0aa4e806a45f633cf826db6cf95d65",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-001ab783b0a5c737a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "prbh6aueanow59j1bmql7gpt"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-749903ca081507f374b03e68c4b104cf",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0c2cf40e7ebd7d2c5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eti8xtfi2e83r6zqobgbhtyjn"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-ab7d0cd195c8b21e52fd73bcd6ad3f6a",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0c270163f9e432235"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "el3fld53lllmhv3vb1sbuidbv"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-af0aae7bccb740a539c0725d23bda135",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-01d1fca973a4a682a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b83v8tl2reqy9c29ibtwwuauj"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-10-0-0-206.eu-west-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "ankara123"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-6c0aa4e806a45f633cf826db6cf95d65"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-6c0aa4e806a45f633cf826db6cf95d65",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-001ab783b0a5c737a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "gz1fc2g8cs4bqjturobx53ur"
          }, {
            "name" : "secret_key",
            "value" : "VIt0XkVe0Ivkd28jsNSgbGQCFIHxXz"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-10-0-0-206.eu-west-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "ankara123"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "895483904"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-6c0aa4e806a45f633cf826db6cf95d65",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-001ab783b0a5c737a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "79y6zag7cruuh83pn4ha12tnk"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          }, {
            "name" : "mapreduce_map_cpu_vcores",
            "value" : "2"
          }, {
            "name" : "mapreduce_map_java_opts_max_heap",
            "value" : "1717986918"
          }, {
            "name" : "mapreduce_map_memory_mb",
            "value" : "2048"
          }, {
            "name" : "mapreduce_reduce_java_opts_max_heap",
            "value" : "3435973837"
          }, {
            "name" : "mapreduce_reduce_memory_mb",
            "value" : "4194304"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "10977"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4096"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_fs_scheduled_allocations",
          "value" : "{\"defaultFairSharePreemptionThreshold\":null,\"defaultFairSharePreemptionTimeout\":null,\"defaultMinSharePreemptionTimeout\":null,\"defaultQueueSchedulingPolicy\":\"drf\",\"queueMaxAMShareDefault\":null,\"queueMaxAppsDefault\":null,\"queuePlacementRules\":[{\"create\":true,\"name\":\"specified\",\"queue\":null,\"rules\":null},{\"create\":null,\"name\":\"nestedUserQueue\",\"queue\":null,\"rules\":[{\"create\":null,\"name\":\"default\",\"queue\":\"users\",\"rules\":null}]},{\"create\":null,\"name\":\"default\",\"queue\":null,\"rules\":null}],\"queues\":[{\"aclAdministerApps\":\"*\",\"aclSubmitApps\":\" \",\"allowPreemptionFrom\":null,\"fairSharePreemptionThreshold\":null,\"fairSharePreemptionTimeout\":null,\"minSharePreemptionTimeout\":null,\"name\":\"root\",\"queues\":[{\"aclAdministerApps\":\"*\",\"aclSubmitApps\":\"*\",\"allowPreemptionFrom\":null,\"fairSharePreemptionThreshold\":null,\"fairSharePreemptionTimeout\":null,\"minSharePreemptionTimeout\":null,\"name\":\"default\",\"queues\":[],\"schedulablePropertiesList\":[{\"impalaDefaultQueryMemLimit\":null,\"impalaDefaultQueryOptions\":null,\"impalaMaxMemory\":null,\"impalaMaxQueuedQueries\":null,\"impalaMaxRunningQueries\":null,\"impalaQueueTimeout\":null,\"maxAMShare\":null,\"maxResources\":null,\"maxRunningApps\":null,\"minResources\":null,\"scheduleName\":\"default\",\"weight\":1.0}],\"schedulingPolicy\":\"drf\",\"type\":null},{\"aclAdministerApps\":\"*\",\"aclSubmitApps\":\"*\",\"allowPreemptionFrom\":null,\"fairSharePreemptionThreshold\":null,\"fairSharePreemptionTimeout\":null,\"minSharePreemptionTimeout\":null,\"name\":\"users\",\"queues\":[],\"schedulablePropertiesList\":[{\"impalaDefaultQueryMemLimit\":null,\"impalaDefaultQueryOptions\":null,\"impalaMaxMemory\":null,\"impalaMaxQueuedQueries\":null,\"impalaMaxRunningQueries\":null,\"impalaQueueTimeout\":null,\"maxAMShare\":null,\"maxResources\":null,\"maxRunningApps\":null,\"minResources\":null,\"scheduleName\":\"default\",\"weight\":4.0}],\"schedulingPolicy\":\"drf\",\"type\":\"parent\"}],\"schedulablePropertiesList\":[{\"impalaDefaultQueryMemLimit\":null,\"impalaDefaultQueryOptions\":null,\"impalaMaxMemory\":null,\"impalaMaxQueuedQueries\":null,\"impalaMaxRunningQueries\":null,\"impalaQueueTimeout\":null,\"maxAMShare\":null,\"maxResources\":null,\"maxRunningApps\":null,\"minResources\":null,\"scheduleName\":\"default\",\"weight\":1.0}],\"schedulingPolicy\":\"drf\",\"type\":null}],\"userMaxAppsDefault\":null,\"users\":[]}"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "WVETLhJSOPZFIKX2OQDhpf9i9qQ4T3"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-af0aae7bccb740a539c0725d23bda135",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-01d1fca973a4a682a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "243tvqj0f5e5dy64xp4v3tkea"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-4e19ee9c588f9e21ccccf396da941aea",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0e34aa518703179bc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2l3r9gp4ouvts8lpl4eb05q5u"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-749903ca081507f374b03e68c4b104cf",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0c2cf40e7ebd7d2c5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1rx2b68skbh3u18hmodsrk1b3"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-ab7d0cd195c8b21e52fd73bcd6ad3f6a",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0c270163f9e432235"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8xnm1ufu224gapazmv97sna6"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-af0aae7bccb740a539c0725d23bda135",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-01d1fca973a4a682a"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "45"
          }, {
            "name" : "role_jceks_password",
            "value" : "eor6a0jyswac6xgu15b5zi3m1"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "5367448780"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "895483904"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "895483904"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_client_use_datanode_hostname",
          "value" : "true"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "KF8fSRhTqOoNzI7TJvQaa48aPMIpDN"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "YeTk0BWABCEQ5CjMzTTP2TqxTfwSem"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "fQyRE1ZTDsbBzTp7GO193F2GvkpbWq"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-DATANODE-4e19ee9c588f9e21ccccf396da941aea",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0e34aa518703179bc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9f1o6vm5pzd999xfhzoi7dz8i"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-749903ca081507f374b03e68c4b104cf",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0c2cf40e7ebd7d2c5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7l78scrzmb18e3c5lk73fw2gp"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-ab7d0cd195c8b21e52fd73bcd6ad3f6a",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0c270163f9e432235"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "egbm7fvdtfdemlqesyxgwtttj"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-6c0aa4e806a45f633cf826db6cf95d65",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-001ab783b0a5c737a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eye9tr68bzjaakfjobsugamu4"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-749903ca081507f374b03e68c4b104cf",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0c2cf40e7ebd7d2c5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "gxzl3gvurpu09fvi9insoiwv"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-749903ca081507f374b03e68c4b104cf",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0c2cf40e7ebd7d2c5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "60971fx5kifwbquyp74snffba"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-ab7d0cd195c8b21e52fd73bcd6ad3f6a",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0c270163f9e432235"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bj90lv89lppdxgai4k62brxni"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-af0aae7bccb740a539c0725d23bda135",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-01d1fca973a4a682a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2skqvxr3njdcl53u4ag8l1f2z"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-6c0aa4e806a45f633cf826db6cf95d65",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-001ab783b0a5c737a"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "47"
          }, {
            "name" : "role_jceks_password",
            "value" : "1kfvlcjmbj3q3i1190coe0c12"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-749903ca081507f374b03e68c4b104cf",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0c2cf40e7ebd7d2c5"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "55"
          }, {
            "name" : "role_jceks_password",
            "value" : "22lpqipwdp1lkxfsg30rl460o"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ip-10-0-0-206.eu-west-1.compute.internal"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "ankara123"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-SENTRY_SERVER-af0aae7bccb740a539c0725d23bda135",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "i-01d1fca973a4a682a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bu5jkv7cdmld57cyoh59acdny"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-01d1fca973a4a682a",
    "ipAddress" : "10.0.0.106",
    "hostname" : "ip-10-0-0-106.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0c270163f9e432235",
    "ipAddress" : "10.0.0.149",
    "hostname" : "ip-10-0-0-149.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0c2cf40e7ebd7d2c5",
    "ipAddress" : "10.0.0.173",
    "hostname" : "ip-10-0-0-173.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-001ab783b0a5c737a",
    "ipAddress" : "10.0.0.206",
    "hostname" : "ip-10-0-0-206.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0e34aa518703179bc",
    "ipAddress" : "10.0.0.93",
    "hostname" : "ip-10-0-0-93.eu-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__f89d1329-0b59-45e3-9546-8307112beea9",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "dbbef673c54b715e74b6bcda11e2b4c052c7eddef4fb692dadc966d737ea82a9",
    "pwSalt" : 8744897496364874132,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-6c0aa4e806a45f633cf826db6cf95d65",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "952244ceeb42b6d17a7928a516aef25c4771896605d22cab3249f1782ee32db4",
    "pwSalt" : -2903657218108886058,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-6c0aa4e806a45f633cf826db6cf95d65",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "ddd26f05af8a41cd7a42946f06a60c40b8363e3c8d04792b348e95cc16f9375c",
    "pwSalt" : 7531355934445627951,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-6c0aa4e806a45f633cf826db6cf95d65",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "56138a89e30f9eaeea9c7980ed8b6ecfcce0f2fa8435741febc52c35ba8ef95e",
    "pwSalt" : -3524293488246321956,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-6c0aa4e806a45f633cf826db6cf95d65",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "2e82b5f7ef056f0fb9ed0c2a57f55274d31bb129a7c1ca9490e830303e57b9bf",
    "pwSalt" : -7658340112959522252,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "a987c9ec723ca643b84a1ec2f5baf29681bda643d7a2b30e62b98af144a85495",
    "pwSalt" : -6021203968658247191,
    "pwLogin" : true
  }, {
    "name" : "andrzej-jedrzejewski",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "e56a315ba5b43d3e3a892171d903dd1c36467669bb86bde61bb0c16f3b8d6f24",
    "pwSalt" : -1442544321530336285,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "af1cf3aafb2fdbd95af110326464b613bf96361b21bb3008002bda7b755c87d9",
    "pwSalt" : -9172557592120647611,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1013",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "895483904"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-10-0-0-206.eu-west-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rpman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "ankara123"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rpman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "895483904"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-6c0aa4e806a45f633cf826db6cf95d65",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-001ab783b0a5c737a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "87dy7mbnvbxwv1g1b1hyyookt"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-6c0aa4e806a45f633cf826db6cf95d65",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-001ab783b0a5c737a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ciof2yn7ukxn6j46tje027sgv"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-6c0aa4e806a45f633cf826db6cf95d65",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-001ab783b0a5c737a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "4eztesatsm2uv74wwaflwtf7d"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-6c0aa4e806a45f633cf826db6cf95d65",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-001ab783b0a5c737a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "copw2u53g3fy5yujox1a55g5n"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-6c0aa4e806a45f633cf826db6cf95d65",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-001ab783b0a5c737a"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1dg1msl1xwqwo3xf2agu5kdcs"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/23/2012 13:20"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
```