## 1. Introduction
This Terraform template deploys a single/standalone FortiAnalyzer into an existing environment.

## 2. Deployment Overview

The Template deploys following components:
- 1 regional subnet into existing VCN
- 1 FortiAnalyzer-VM instance with 1 vNIC
- 1 route table associated with regional subnet and an NSG

## 3. Deployment Steps

Before starting deployment, **following values are required**. All other settings can be modified.
- Existing VCN OCID
- Existing VCN CIDR block (example: 10.1.0.0/16)
- Existing Internet Gateway OCID (if there is no IGW, it should be created in advance)

One of the two methods can be used to deploy FortiAnalyzer Standalone solution in OCI.

### 3.1 Quick Deployment Using OCI Stacks service

Following links are prepared to deploy FortiAnalyzer Standalone solution in a specific region. You can select required FortiAnalyzer OS version to proceed. Since buttons will be re-directing to use OCI Stacks service, user should be already logged into OCI Dashboard.

##### BYOL Images

|v6.4.10|v7.0.5|v7.2.1
|:-:|:-:|:-:|
|[![Deploy to Oracle Cloud](https://oci-resourcemanager-plugin.plugins.oci.oraclecloud.com/latest/deploy-to-oracle-cloud.svg)](https://cloud.oracle.com/resourcemanager/stacks/create?zipUrl=https://github.com/40net-cloud/fortinet-oci-solutions/releases/download/fazstandalone/FAZ_Standalone_ExistingVCN_v6.4.10_BYOL.zip)|[![Deploy to Oracle Cloud](https://oci-resourcemanager-plugin.plugins.oci.oraclecloud.com/latest/deploy-to-oracle-cloud.svg)](https://cloud.oracle.com/resourcemanager/stacks/create?zipUrl=https://github.com/40net-cloud/fortinet-oci-solutions/releases/download/fazstandalone/FAZ_Standalone_ExistingVCN_v7.0.5_BYOL.zip)|[![Deploy to Oracle Cloud](https://oci-resourcemanager-plugin.plugins.oci.oraclecloud.com/latest/deploy-to-oracle-cloud.svg)](https://cloud.oracle.com/resourcemanager/stacks/create?zipUrl=https://github.com/40net-cloud/fortinet-oci-solutions/releases/download/fazstandalone/FAZ_Standalone_ExistingVCN_v7.2.1_BYOL.zip)

### 3.2. Manual Deployment Using Terraform CLI

Pre-requisite to proceed: Terraform-CLI should be downloaded already. 

1. Download the files in a local folder or clone the repository using command below:</br>
```
https://github.com/40net-cloud/fortinet-oci-solutions.git
```
2. Navigate to required folder that includes "_.tf_" files. (path: fortinet-oci-solutions > FortiAnalyzer  > Existing-VCN > BYOL)
3. FortiAnalyzer license can be activated using web gui.
4. Edit _terraform.tfvars_ file with required fields (tenancy_ocid, compartment_ocid, region etc.)
5. Initialize the Terraform using following command
```
terraform init
```
6. Use plan option to double check if there is no error/warning in the code.
```
terraform plan
```
7. Apply Terraform state.
```
terraform apply
```
