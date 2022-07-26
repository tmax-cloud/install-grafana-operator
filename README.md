
# Grafana-operator 설정 가이드

## 개요
* grafana 관리
* Hyperauth와 연동하여 user 별 dashboard 제공 가능.

## 사전 요구사항(권장, 필수아님)
* single operator 5.0.29.0 이상 버전 부터 호환(k8s version 1.22)
* single operator 5.0.26.3 이상 버전 부터 호환(k8s version 1.19)
* hypercloud api server는 5.0.29.1 이상 버전 부터 호환

## 구성 요소
* grafana-operator (tmaxcloudck/grafana-operator:v0.0.3)

## Step 0. grafana-operator 설치
* 목적 : grafana-operator 설치
* 순서 : 
1. grafana-operator 이미지설정
([setup](https://github.com/tmax-cloud/install-grafana-operator/tree/main/yaml/setup)) 폴더에 grafana-operator-deployment.yaml에 이미지 버전 설정

2. kubectl apply -f ./setup 하여 설치

## Step 1. Grafana CR 생성

* 목적 :
* 순서: 

## (Optional)Dashboard CR 생성 방법
