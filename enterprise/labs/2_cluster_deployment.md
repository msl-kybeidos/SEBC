```json
{
  "timestamp" : "2016-11-17T19:45:52.142Z",
  "clusters" : [ {
    "name" : "msl-kybeidos",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "527433728"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "527433728"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3545550028"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "596"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-11-226.eu-central-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-2c31e939b6b49e7dd0e96f5c3237d142",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-7768f2ca"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-4463814a244af83ef9b92ff60e1ca79d",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-7468f2c9"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-45a2f8805384bf790a5bace5bf79fe0b",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-7668f2cb"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-fcaff36ec575542b2df656bcf259dd33",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-7168f2cc"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2sy94562hfj6ey2178j3g1d0w"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8pss643frppltliq6gjl2ehn3"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "527433728"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-45a2f8805384bf790a5bace5bf79fe0b",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-7668f2cb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "210bj2bnumksajc77ufl5jiuv"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5g1qwtbvuiqxhw8t30u465fkl"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-fcaff36ec575542b2df656bcf259dd33",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-7168f2cc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "88e1bh85czlvqvpd40gie7qih"
          }, {
            "name" : "serverId",
            "value" : "2"
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
          "value" : "ip-172-31-11-226.eu-central-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue_password"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-a4bd3b60c39044b8e2c8ef57e838f436"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eoso660l3d59uq0mhguka6o5o"
          }, {
            "name" : "secret_key",
            "value" : "BORwD4ri8ylSA7Upck7pn9wzylloeW"
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
            "value" : "ip-172-31-11-226.eu-central-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_password"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "527433728"
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
        "name" : "oozie-OOZIE_SERVER-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d66igliv3nveiyzr0et110bbx"
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
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "527433728"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
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
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "2886"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "527433728"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4527"
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
          "name" : "yarn_service_cgroups",
          "value" : "true"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "8vOcO8AQDI2UanlVzjJ7e1Y6O7yhBh"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-GATEWAY-2c31e939b6b49e7dd0e96f5c3237d142",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-7768f2ca"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-GATEWAY-4463814a244af83ef9b92ff60e1ca79d",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-7468f2c9"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-GATEWAY-45a2f8805384bf790a5bace5bf79fe0b",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-7668f2cb"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-GATEWAY-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-GATEWAY-fcaff36ec575542b2df656bcf259dd33",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-7168f2cc"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dnxzr120y3yskzhb424tab6uw"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-2c31e939b6b49e7dd0e96f5c3237d142",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-7768f2ca"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ce1xunr3m9f6i7nkr4n4fl4c8"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-4463814a244af83ef9b92ff60e1ca79d",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-7468f2c9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "hlw3tg2aa4s2nxcy4lvo6smy"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-45a2f8805384bf790a5bace5bf79fe0b",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-7668f2cb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b625tpgu2va0kyxh3s88kyqt"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-fcaff36ec575542b2df656bcf259dd33",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-7168f2cc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1healx6rvdlxvqvkdisn2my8w"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "57"
          }, {
            "name" : "role_jceks_password",
            "value" : "3updtjqljk6ric3jju6q90yjf"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "527433728"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "10555414937"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/hdfs_journal"
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
            "value" : "527433728"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "527433728"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_client_use_datanode_hostname",
          "value" : "true"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "QMiXjQonFehp2fgdQlPOuTK4cbcrPS"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "wRYk9cgaYEcw5ubVR2nUn2pyBTbq9U"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "AROvOuJbQGNKNaPHSjBrd6m5xI0gaw"
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
        "name" : "hdfs-BALANCER-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-2c31e939b6b49e7dd0e96f5c3237d142",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-7768f2ca"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2rufqewhhxt44st7m3509f083"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-4463814a244af83ef9b92ff60e1ca79d",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-7468f2c9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5qg2j52pkxm0zkh2st0ova3oe"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-45a2f8805384bf790a5bace5bf79fe0b",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-7668f2cb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1agls5wax02z5g03aw55dpvpa"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-fcaff36ec575542b2df656bcf259dd33",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-7168f2cc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7lsb6qugars929fcas2iifbr3"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5tw9t0lamrhdujo24qrs0c3fk"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-fcaff36ec575542b2df656bcf259dd33",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-7168f2cc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9bce881cc9421b5dp19i8oqqv"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b8exp5dcv3ro62ebu8fl7uwqx"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-2c31e939b6b49e7dd0e96f5c3237d142",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-7768f2ca"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "42djzp24ep5oaqkkqrpfg862k"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-4463814a244af83ef9b92ff60e1ca79d",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-7468f2c9"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1uhlfdisgshkr39z79sygihzs"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-45a2f8805384bf790a5bace5bf79fe0b",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-7668f2cb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cwl6kiodd1k1w452uzktbk3z6"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "311arvweuvzoje7a4mhbi4eej"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-fcaff36ec575542b2df656bcf259dd33",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-7168f2cc"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1cww1gsbb2xx0he8otgsptgdx"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-a4bd3b60c39044b8e2c8ef57e838f436",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-7068f2cd"
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
            "value" : "59"
          }, {
            "name" : "role_jceks_password",
            "value" : "83qujnjiunzzzgfyliker19vi"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-fcaff36ec575542b2df656bcf259dd33",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-7168f2cc"
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
            "value" : "70"
          }, {
            "name" : "role_jceks_password",
            "value" : "bm9uk1cugqdthy4tiul9h4fun"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-7068f2cd",
    "ipAddress" : "172.31.11.226",
    "hostname" : "ip-172-31-11-226.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-7168f2cc",
    "ipAddress" : "172.31.11.227",
    "hostname" : "ip-172-31-11-227.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-7668f2cb",
    "ipAddress" : "172.31.11.228",
    "hostname" : "ip-172-31-11-228.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-7768f2ca",
    "ipAddress" : "172.31.11.229",
    "hostname" : "ip-172-31-11-229.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-7468f2c9",
    "ipAddress" : "172.31.11.230",
    "hostname" : "ip-172-31-11-230.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-a4bd3b60c39044b8e2c8ef57e838f436",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "9d83c2ba6e93177d6469433d2d47cc7f81228cc21009017e193ee8248743afc6",
    "pwSalt" : 8733722811594971093,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-a4bd3b60c39044b8e2c8ef57e838f436",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "6bc539ef4dd4d33325ced0f94291bc65c846e1289cf2b196f84a5e86312cfc5a",
    "pwSalt" : -7717037245025558264,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-NAVIGATOR-a4bd3b60c39044b8e2c8ef57e838f436",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "5b433a105714eb76fb39c13d5e54b16dc9fa6052b3b8332704fed8f14d336c0b",
    "pwSalt" : -7252308955756753016,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-NAVIGATORMETASERVER-a4bd3b60c39044b8e2c8ef57e838f436",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "b4fa8a857a5f4eb0d7cb6443e83b49bd3df596881793f808aeaf8e30b1e2dd91",
    "pwSalt" : 3980445206395969986,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-a4bd3b60c39044b8e2c8ef57e838f436",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "77b153d96bfd561b1fd88a6268bc317d151898f55ced131e812d83950786d76f",
    "pwSalt" : -9059572216045786764,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-a4bd3b60c39044b8e2c8ef57e838f436",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "7cd07016ad2cde6517bf92c1966c0e1efa91eddfabec43d5d88c925432f5de92",
    "pwSalt" : -7802085449056340269,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "da52a545ff7f99e0a425a6e6bd337d295a3631d346673e0490cc9d53fd82a04a",
    "pwSalt" : -1920209196898555120,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "52e3cba84f5056650ecd800602d907cbc252a6331eec508a098c8412af02a745",
    "pwSalt" : -6376519602974089102,
    "pwLogin" : true
  }, {
    "name" : "msl-kybeidos",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "f24ff73bddfb76bf708a984737dd07be5fce5249824b52ef3aa49b9efdb72ab0",
    "pwSalt" : -4062920370162591094,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20160916-1426",
    "gitHash" : "d23c620f3a3bbd85d8511d6ebba49beaaab14b75",
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
          "value" : "527433728"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "527433728"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      }, {
        "roleType" : "NAVIGATOR",
        "items" : [ {
          "name" : "navigator_database_host",
          "value" : "ip-172-31-11-226.eu-central-1.compute.internal"
        }, {
          "name" : "navigator_database_password",
          "value" : "nav_password"
        }, {
          "name" : "navigator_heapsize",
          "value" : "527433728"
        } ]
      }, {
        "roleType" : "NAVIGATORMETASERVER",
        "items" : [ {
          "name" : "nav_metaserver_database_host",
          "value" : "ip-172-31-11-226.eu-central-1.compute.internal"
        }, {
          "name" : "nav_metaserver_database_password",
          "value" : "navms_password"
        }, {
          "name" : "navigator_heapsize",
          "value" : "536870912"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-11-226.eu-central-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "527433728"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "527433728"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-a4bd3b60c39044b8e2c8ef57e838f436",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-7068f2cd"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9qs2nx7omw9qza6x6l7afy85f"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-a4bd3b60c39044b8e2c8ef57e838f436",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-7068f2cd"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "89hpe7rzgk8ltz4ckumvlxu3d"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-a4bd3b60c39044b8e2c8ef57e838f436",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-7068f2cd"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8u28jlguvbt3s8rd9q8odzshk"
        } ]
      }
    }, {
      "name" : "mgmt-NAVIGATOR-a4bd3b60c39044b8e2c8ef57e838f436",
      "type" : "NAVIGATOR",
      "hostRef" : {
        "hostId" : "i-7068f2cd"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6s8nvw70f8obkazw9jaxg3p1y"
        } ]
      }
    }, {
      "name" : "mgmt-NAVIGATORMETASERVER-a4bd3b60c39044b8e2c8ef57e838f436",
      "type" : "NAVIGATORMETASERVER",
      "hostRef" : {
        "hostId" : "i-7068f2cd"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3jlh25kx8w3edhpoypgsvtgii"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-a4bd3b60c39044b8e2c8ef57e838f436",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-7068f2cd"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "189n46d0fpmabbuf2qzq0yfop"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-a4bd3b60c39044b8e2c8ef57e838f436",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-7068f2cd"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3i18gaqpy4z8u4o3w12rrur1q"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/27/2012 8:10"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```