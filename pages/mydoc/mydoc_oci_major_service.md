---
title: OCI 주요 서비스
tags: [oci]
keywords: oci
last_updated: July 16, 2016
summary: "Oracle Cloud를 새로 접하시는 분들을 위하여 Oracle Cloud에서 자주 사용하는 Oracle Cloud 핵심 용어를 간단하게 정리합니다."
sidebar: mydoc_sidebar
permalink: mydoc_oci_major_service.html
folder: mydoc
---

## OCI 주요 용어
OCI이 완전 입문자를 위하여 Oracle Cloud에서 자주 사용되는 용어를 정리합니다.

### Oracle Cloud Infrastructure 
Orale Cloud Infrasturcture는 2018년부터 사용하기 시작한 Oracle Cloud의 새로운 브랜드명입니다. 초기에 오라클은 Nimbula를 인수하여 클라우드 서비스를 개발하였고, 2014년 Oracle은 OPC(Oracle Public Cloud)라는 브랜드로 클라우드 서비스를 시작했습니다. 이 시점부터 오라클은 새로운 2세대 클라우드 아키텍처를 개발하기 시작했습니다. 오라클의 2세대 클라우드 아키텍처로 개발된 오라클 클라우드 서비스가 바로 Oracle Cloud Infrastructure(이하 OCI)입니다. 2018년 Oracle Cloud 인프라 구현 기술은 OCI로 전면 교체되었고, 동시에 오라클 클라우드 브랜드명도 OPC(Oracle Public Cloud)에서 OCI(Oracle Cloud Infrastructure)로 변경되었습니다.

### 리전(Region)과 AD(Availability Domains) 
Oracle Cloud Infrastructure(OCI)는 리전(Region)과 AD(Availability Domains)에서 운영됩니다. 리전은 데이터 센터가 운영되는 지리적인 영역을 나타냅니다. 그리고 AD는 리전을 구성하고 실제 OCI 서비스가 운영되는 데이터 센터입니다. 각 OCI 리전은 1개에서 최대 3개 AD로 구성됩니다. 리전은 오라클 클라우드가 서비스되는 물리적 데이터 센터인 AD를 묶는 논리적 단위입니다. 따라서 서비스 지역의 물리적 AD를 추상화하는 서비스 거점의 의미가 있습니다. 리전은 완전히 독립된 OCI 최상위 단위입니다. 각 리전은 네트워크로 연결될 뿐 모든 서비스와 자원은 완전히 격리됩니다.

2020년 1월 12일 현재 Commercial Region을 12개를 운영하고 있습니다. 2020년 말까지 Commercial Region과 Government Region을 합쳐 총 36개까지 확대할 예정에 있습니다. 다음은 2020년 말 기준 OCI 리전 지도입니다.



리전을 구성하는 각 AD는 어떤 자원도 공유하지 않는 물리적으로 완전히 독립된 데이터 센터입니다. 리전을 구성하는 AD은 파워와 네트워크 등 어떤 물리적 자원도 공유하지 않습니다. 따라서 특정 AD 장애가 다른 AD로 파급되지 않습니다. AD는 Region 고가용성을 위한 설계입니다.



### OCI 콘솔(Console) 
OCI 자원을 관리하고 접근하기 위해서 제공하는 웹 기반 UI입니다.



### Tenancy(테넌시) 
OCI에 계정(Account)을 생성하면, 해당 계정(Account)을 위한 Tenancy가 생성됩니다. OCI에서 테넌시는 완전히 독립되고 격리된 사용자 기준의 최상위 단위입니다. OCI에 생성된 계정이 바로 Tenancy라고 말할 수 있습니다.

### Compartment(컴파트먼트) 
컴파트먼트는 클라우드 자원을 구성하고 접근 제어하기 위한 논리적인 단위입니다. OCI에서 만들어지는 대부분 자원은 특정 컴파트먼트에 할당됩니다. OCI 자원에는 VM 인스턴스, VCN(Virtual Cloud Networks), 블록 볼륨 등이 있습니다. 모든 OCI 자원은 특정 Compartment에 할당되고, Compartment 단위로 OCI User Group(사용자 그룹) 단위로 사용자 접근 정책이 설정 및 관리됩니다. 컴파트먼트는 물리적으로 실체가 있는 오브젝트가 아닌 논리적인 그룹입니다.

OCI 계정이 생성될 때 Tenancy가 생성됩니다. 이 Tenancy가 루트 컴파트먼트(Root Compartment)입니다. 루트 컴파트먼트(Root Compartment)는 최상의 컴파트먼트입니다. 파일 시스템의 루트 디렉터리(/)와 비슷합니다. 디렉터리 구조와 같이 Root Compartment 아래에 새로운 Compartment를 추가할 수 있습니다.



### Virtual Cloud Network(VCN) 
Virtual Cloud Network (VCN)은 서브넷, 라우트 테이블과 게이트웨이로 구성되는 전통적인 네트워크의 가상화 버전입니다. VCN은 리전 범위의 자원입니다. VCN은 특정 리전에 종속됩니다. VCN을 구성하는 서브넷(Subnet)을 만들 때, 리전 범위와 AD 범위를 선택할 수 있습니다. 리전 범위로 지정하면 리전을 구성하는 모든 AD에 걸쳐 서브넷이 구성됩니다. AD 범위를 지정하면 특정 AD에 위치합니다.



VCN는 다음과 같은 컴포넌트로 구성됩니다.

Subnet
public subnet: 서브넷에 포함되는 VM 인스턴스에 Public IP 설정 가능
private subnet: 서브넷에 포함되는 VM 인스턴스가 Public IP를 갖지 못함
Internet Gateway: 인터넷 연결 관문
Route Table: VCN을 위한 가상의 라우트 테이블
Security Lists: VCN의 가상 방화벽

### Bare Metal Host 
OCI가 제공하는 사용자가 직접 제어 가능한 물리적인 서버가 Bare Metal Host입니다. Bare Metal Host에 하이퍼바이저 없이 Bere Metal 서버를 돌릴 수 있습니다. 이렇게 동작하는 서버를 Bare metal compute instances라고 합니다. OCI 사용자가 직접 물리적 CPU, 메모리, NIC(Network Interface Card)를 관리 할 수 있습니다. 이렇게 관리하는 자원은 다른 테넌트와 어떠한 자원도 공유하지 않습니다.

### Instance(인스턴스) 
OCI에서 동작하는 VM을 인스턴스라고 합니다.

### Image(이미지) 
Image는 인스턴스를 위해서 운영체제와 여러 소프트웨어를 정의하는 가상 하드웨어 드라이브 템플릿입니다. OCI에서 인스턴스를 구동시킬 때, 이미지를 선택합니다. OCI는 다양한 이미지를 제공하며, OCI 사용자는 추가로 사용자 정의 이미지를 등록하고 사용할 수 있습니다.



### Shape 
Shape은 인스턴스에 할당하는 컴퓨팅 자원(CPU, Memory 등) 템플릿입니다. 다음은 OCI가 제공하는 여러 Shape 중에서 Standard Shape 목록입니다.



### Key Pair 
Key Pair(키 페어)는 OCI가 사용하는 인증 방식입니다. Key Pair(키 페어)는 개인 키(private key) 파일과 공개 키(public key) 파일로 구성됩니다. 공개 키는 OCI에 업로드됩니다. OCI 사용자는 개인 키를 패스워드처럼 비공개로 관리합니다.

여러 스펙으로 Key Pair(키 페어)를 만들 수 있습니다. OCI는 목적에 따라 두 가지 유형의 Key Pair(키 페어)를 사용합니다.

인스턴스 SSH Key Pair(키 페어)
인스턴스 SSH Key Pair(키 페어)는 VM 인스턴스에 SSH 접속에 사용됨.
인스턴스를 프로비저닝할 때, 공개 키(public key)를 등록.
등록된 공개 키(public key)는 인스턴스의 기본 OS 계정의 authorized key 파일에 저장
인스턴스의 기본 OS 계정: 오라클 리눅스(oci), 우분투(ubuntu)
ssh 접속 시, 사용자의 개인 키(Private Key)를 authorized key 파일에 저장된 공개 키로 검증.
API signing key pair(API 서명 키 페어)
API signing key pair는 PEM 포멧을 사용.
API 요청을 제출할 때 사용자 인증에 사용.
REST API로 OCI를 접속하는 사용자가 사용.
다음 그림은 OCI 사용자에 API 서명 키 페어를 등록하는 화면입니다.



### 블록 볼륨(BLOCK VOLUME) 
블록 볼륨은 OCI 인스턴스에 영구적인 저장 공간을 제공하는 가상 디스크입니다. 기존에 물리적 하드 디스크 드라이브를 사용했던 것 처럼, 클라우드 인스턴스에서는 블록 볼륨을 사용합니다. OCI 사용자는 데이터 유시 없이 인스턴스에 볼륨을 분리해서 다른 인스턴스에 붙일수 있습니다.



### Object Storage 
오브젝트 스토리지(Object Storage)는 객체로 데이터를 저장하고 관리하는 스토리지 아키텍처입니다. 모든 데이터 타입을 저장할 수 있습니다. 최대 객체 사이즈는 10TB입니다. Object Storage에 저장되는 최대 파일 사이즈는 50GB입니다. 50GB보다 큰 객체는 여러 파일로 분할되어 저장됩니다. 오브젝트 스토리지에는 변경 빈도가 낮은 데이터가 저장됩니다. 다음과 같은 용도로 사용됩니다.

### 데이터 백업
파일 공유
로그나 센서 데이터와 같은 비정형 데이터 저장
버킷(BUCKET) 
버킷은 오브젝트 스토리지(Object Storage)에 저장되는 데이터와 파일을 묶는 논리적인 그룹입니다. 버킷에 저장되는 객체 수는 제한이 없습니다.

### OCID(ORACLE CLOUD IDENTIFIER) 
모든 OCI 자원은 유일한 ID를 갖습니다. 이 ID가 Oracle Cloud Identifier(OCID)입니다. 이 ID에는 자원 정보가 포함됩니다.

## 참고 문서
[OCI Official Documentation 사이트](https://docs.oracle.com/en-us/iaas/Content/GSG/Concepts/concepts.htm){:target="_blank"} Key Concepts and Terminology<br/>
[k21academy](https://k21academy.com/oracle-compute-cloud-services-iaas/oracle-cloud-infrastructure-oci-region-ad-tenancy-compartment-vcn-iam-storage-service/) Oracle Cloud Infrastructure (OCI) : Region, AD, FD, Tenancy, Compartment, VCN, IAM, Storage Service<br/>
[OCI 100 Training](https://www.oracle.com/a/ocom/docs/cloud/virtual-cloud-network-100.pdf) Virtual Cloud Network

{% include links.html %}
