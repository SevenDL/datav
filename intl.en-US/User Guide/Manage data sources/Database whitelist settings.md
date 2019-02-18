# Database whitelist settings {#concept_hcq_ymz_q2b .concept}

Before you can add a data source, you must configure a whitelist for your database to ensure that DataV has access to it.

-   If you are using a data source from Alibaba Cloud RDS database, see [Set whitelist](https://www.alibabacloud.com/help/doc-detail/43186.html). Add the following IP addresses to the whitelist of your RDS database.
-   If you are using a data source from Alibaba Cloud ECS database, you must add the following IP addresses to the whitelist of the ECS [security group rules](https://www.alibabacloud.com/help/doc-detail/25471.html), system firewalls, and your database.
-   If you are using a data source from the database on a local physical machine, you must add the following IP addresses to the whitelist of the system firewalls of this physical machine, the network firewalls, and your database.

According to your [database connection scenarios](https://www.alibabacloud.com/help/doc-detail/26195.html), add following IP addresses to the whitelist of your database.

## Singapore {#section_zzb_vnz_q2b .section}

-   Internet:
    -   47.88.235.235/0
    -   47.74.136.56/0
    -   47.88.250.141/0
    -   47.88.235.217/0
    -   47.74.136.64/0
    -   47.74.136.22/0
    -   47.74.136.12/0
    -   47.88.235.207/0
-   Intranet classic network \(you must modify 11 network segment routing\):
    -   11.193.8.8/0
    -   11.192.152.94/0
    -   11.193.8.55/0
    -   11.193.8.59/0
    -   10.152.165.219/0
    -   11.192.152.89/0
    -   11.192.152.117/0
    -   11.193.8.60/0
-   Intranet VPC network:

    100.104.13.0/24


## Malaysia {#section_cnh_wnz_q2b .section}

-   Internet:

    47.254.212.25/0

-   Intranet classic network:
    -   11.193.189.75/0
    -   11.193.189.69/0
    -   11.193.189.73/0
    -   11.193.189.72/0
-   Intranet VPC network

    100.104.133.64/26


## Japan \(Tokyo\) {#section_qyz_csj_z2b .section}

-   Internet:
    -   47.91.9.73/0
    -   47.91.13.92/0
    -   47.91.9.1/0
    -   47.91.9.42/0
-   Intranet classic network:
    -   11.192.149.155/0
    -   11.192.149.118/0
    -   11.192.147.75/0
    -   11.192.149.66/0
-   Intranet VPC network:

    100.104.175.0/24


## Germany {#section_qyz_ksj_z2b .section}

-   Internet:
    -   47.91.83.106/0
    -   47.91.82.104/0
    -   47.91.84.120/0
    -   47.91.84.16/0
    -   47.91.84.36/0
-   Intranet classic network
    -   11.192.169.2/0
    -   11.192.168.143/0
    -   11.193.107.16/0
    -   11.192.170.80/0
    -   11.192.170.221/0
-   Intranet VPC:

    100.104.244.192/26


## Solution to disconnection of 11 network segments. {#section_gf1_5sj_z2b .section}

If you encounter the disconnection of 11 network segments, execute the following command to add a router in /etc/rc.local.

```
sudo route add -net 11.0.0.0/8 gw 10.152.28.247
```

**Note:** The IP address behind gw is the server gateway.

If the problem is unresolved, you can open a ticket and send it to ECS to inform Alibaba Cloud technical support engineers that the 11 network segments are unable to access your server.

