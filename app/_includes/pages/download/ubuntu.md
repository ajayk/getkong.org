{% capture cassandra_version %}{{site.data.kong_latest.dependencies.cassandra}}{% endcapture %}

### Ubuntu 12.04/14.04

1. **Installation:**

    Add the right source to APT for Ubuntu 12.04:

    ```bash
    echo "deb [arch=amd64] http://mashape-kong-apt-repo.s3-website-us-east-1.amazonaws.com/ubuntu/12_04/ kong main" | sudo tee -a /etc/apt/sources.list
    ```

    Add the right source to APT for Ubuntu 14.04:

    ```bash
    echo "deb [arch=amd64] http://mashape-kong-apt-repo.s3-website-us-east-1.amazonaws.com/ubuntu/14_04/ kong main" | sudo tee -a /etc/apt/sources.list
    ```

    Then execute:

    ```bash
    apt-get update
    apt-get install kong
    ```

2. **Start Kong:**

    Before starting Kong, make sure [Cassandra v{{cassandra_version}}](http://cassandra.apache.org/) is running and [`kong.yml`](/docs/{{site.data.kong_latest.version}}/configuration) points to the right Cassandra server. Then execute:

    ```bash
    kong start
    ```

3. **Kong is running:**

    ```bash
    curl http://127.0.0.1:8001
    ```

4. **Getting Started**

    Quickly learn how to use Kong with the [5-minute Quickstart](/docs/{{site.data.kong_latest.version}}/quickstart).