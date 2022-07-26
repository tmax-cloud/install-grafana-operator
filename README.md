
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

* 목적 : grafana CR 설정
* 순서: 
1. Grafana.yaml에서 spec.config.server.domain에 grafana ingress 작성(ex grafana.tmaxcloud.org)
2. spec.config.log.level 에 log level 설정
3. spec.config.auth.generic_oauth에 client_id = grafana(고정), client_secret = hyperauth grafana client에서 긁어오기, 
   auth_url = https://{hyperauth_address}/auth/realms/tmax/protocol/openid-connect/auth, 
   token_url = https://{hyperauth_address}/auth/realms/tmax/protocol/openid-connect/token, 
   api_url = https://{hyperauth_address}/auth/realms/tmax/protocol/openid-connect/userinfo

## (Optional)Dashboard CR 생성 방법
