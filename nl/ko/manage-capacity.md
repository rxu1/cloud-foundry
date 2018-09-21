---

copyright:
  years: 2018
lastupdated: "2018-08-15"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}

# 리소스 사용량

관리자와 개발자는 애플리케이션 및 셀에서 사용되는 CFEE의 리소스 용량(메모리 및 CPU)을 확인할 수 있습니다. CFEE 환경에서 리소스 사용량을 모니터하려면 다음을 수행하십시오.

1. [{{site.data.keyword.Bluemix_notm}} Cloud Foundry 환경 대시보드](https://console.bluemix.net/dashboard/cloudfoundry?filter=cf_environments)로 이동하여 리소스 사용량을 관리하려는 {{site.data.keyword.cfee_full_notm}}를 여십시오.
2. {{site.data.keyword.cfee_full_notm}} 사용자 인터페이스에서 왼쪽 탐색 분할창에 있는 **리소스 사용량** 항목으로 이동하여 _리소스 사용량_ 페이지를 여십시오. _리소스 사용량_ 페이지에서 _애플리케이션_ 또는 _셀_ 하위 항목으로 이동하여 해당 페이지를 열 수 있습니다. _애플리케이션_ 및 _셀_ 페이지에 표시된 정보는 리소스 사용량을 분류하는 두 가지 방법으로 간주될 수 있습니다.
   * **애플리케이션** 페이지는 인스턴스에 걸쳐 집계된 리소스 사용량을 애플리케이션별로 분석합니다.
   * **셀** 페이지에는 특정 셀에서 실행 중인 애플리케이션 인스턴스의 리소스 사용량이 표시됩니다. 셀 간의 리소스 사용량 패턴은 용량 및 로드 분산에 대한 통찰력을 제공할 수 있습니다. 예를 들어, 애플리케이션의 로드 밸런싱(예: 셀 간에 애플리케이션에서 사용된 사용량에 큰 차이가 있는 경우) 또는 전체 용량에 근접한 리소스 사용량(예: 모든 셀의 리소스 사용량 백분율이 큰 경우)에 대한 문제점을 식별하는 데 도움이 될 수 있습니다.

**참고:** 리소스 사용량 데이터는 최근 5분 콜렉션 주기 동안의 리소스 사용량을 표시합니다. 페이지의 맨 위에 있는 **데이터 새로 고치기**를 클릭하여 리소스 사용량 데이터를 새로 고칠 수 있습니다.

## 애플리케이션
{: #usage_apps}

애플리케이션 페이지에는 두 개의 섹션이 있습니다.
1. 다음을 표시하는 메모리 및 CPU에 대한 가로 막대형 차트:
   * CFEE 인스턴스에서 사용할 수 있는 *총 사용 가능* 메모리 및 CPU
   * CFEE 인스턴스의 *모든 앱*에서 사용된 메모리 및 CPU
   * 아래 테이블의 *선택한 앱*에서 사용된 메모리 및 CPU. 

   모든 앱 또는 테이블에서 선택한 앱에서 사용된 메모리 또는 CPU의 백분율을 표시하려면 차트의 해당 부분 위로 마우스를 이동하십시오. 차트의 *모든 앱* 부분 위로 마우스를 이동하면 총 사용 가능 메모리 및 CPU에 대한 사용된 메모리 및 CPU의 백분율이 표시됩니다. 차트의 *선택한 앱* 부분 위로 마우스를 이동하면 총 사용 가능 메모리 및 CPU에 대한 사용된 메모리 및 CPU의 백분율이 표시됩니다. 

2. 모든 애플리케이션을 나열하는 테이블. 테이블의 각 행에는 해당 애플리케이션에 대한 리소스 정보가 표시됩니다. 행을 펼치면 해당 애플리케이션의 다양한 인스턴스에 대한 사용량 정보가 표시됩니다.

  테이블의 첫 번째 열은 해당 애플리케이션이 페이지의 맨 위에 있는 차트에 포함될 *선택한 앱* 세트에 포함되는지 여부를 판별하는 선택란입니다. 애플리케이션을 선택한 세트에 포함(또는 제외)하려면 해당 선택란을 클릭하십시오. 애플리케이션을 세트에 포함하도록 선택하거나 선택 취소하면 그래프가 새로 고쳐집니다. 막대형 차트의 오른쪽에 있는 _선택한 앱_ 범례에는 현재 그래프에 포함하도록 선택된 애플리케이션의 수가 괄호 안에 표시됩니다.

  다음 정보가 애플리케이션 테이블에 열로 표시됩니다.
   * **애플리케이션 이름**: 애플리케이션 또는 애플리케이션 인스턴스의 이름입니다. 사용자에게 애플리케이션에 액세스할 수 있는 권한이 없는 경우 대신 애플리케이션 GUID가 표시됩니다.
   * **인스턴스**: 애플리케이션의 경우 실행 중인 인스턴스의 수를 나타냅니다. 애플리케이션 인스턴스의 경우(애플리케이션 행을 펼치면 애플리케이션 이름 아래에 표시됨) 애플리케이션 인스턴스가 실행되는 셀의 이름을 나타냅니다.
   * **총 메모리-실제**: 애플리케이션의 모든 인스턴스에서 사용된 실제 메모리의 양(MB)입니다. 애플리케이션에서 사용된 실제 메모리는 모든 애플리케이션의 인스턴스에서 사용된 실제 메모리의 합계와 같습니다.
   * **총 메모리-예약됨**: 애플리케이션의 모든 인스턴스에서 예약된 메모리의 양(MB)입니다. 애플리케이션에서 예약된 메모리는 모든 애플리케이션의 인스턴스에서 예약된 메모리의 합계입니다.
   * **평균 CPU(셀의 %)**: 애플리케이션 인스턴스의 경우 이 메트릭은 **애플리케이션 인스턴스가 실행되는 셀 내의** 평균 CPU를 나타냅니다. 애플리케이션의 경우 해당 인스턴스 평균에서의 CPU 사용량 평균을 나타냅니다.
   * **최대 CPU(셀의 %)**: 애플리케이션 인스턴스의 경우 이 메트릭은 **인스턴스가 실행되는 셀 내에서** 해당 인스턴스에서 사용되는 최대 CPU를 나타냅니다. 애플리케이션의 경우 해당 인스턴스의 최대 CPU 사용량 중 가장 높은 값을 나타냅니다.
   * **CPU(시스템의 %)**: CFEE에서 사용 가능한 총 CPU 중에서 애플리케이션 및 해당 인스턴스에서 사용된 CPU의 백분율입니다. 애플리케이션에서 사용되는 CPU는 모든 애플리케이션의 인스턴스에서 사용되는 CPU 백분율의 합계와 같습니다.
   * **평균 요청**: 최근 데이터 콜렉션 주기 동안의 애플리케이션에 대한 수신 요청의 평균 수입니다.
   * **조직**: 애플리케이션이 배치된 조직입니다. 사용자가 조직의 구성원이 아니면 대신 조직 GUID가 표시됩니다.

테이블의 애플리케이션 행을 펼쳐서 애플리케이션 인스턴스 및 해당 리소스 사용량 메트릭의 목록을 확인하십시오.

### 애플리케이션 필터링
테이블 위에 있는 **애플리케이션** 및 **조직** 필터 드롭다운을 통해 테이블의 컨텐츠를 필터링할 수 있습니다.

또한 테이블 위에 있는 필터 입력 필드를 사용하여 필터 필드에 입력하는 문자열과 일치하는 애플리케이션만 표시할 수 있습니다. 필터는 테이블 및 테이블 위의 차트 모두에 반영됩니다.

**참고:** 필터는 위의 차트에 포함된 _선택한 앱_ 세트에 포함하기 위해 첫 번째 열 테이블의 선택란을 통해 선택된 테이블 행과 독립적으로 작동합니다. 예를 들어, CFEE 환경에 총 10개의 애플리케이션이 있고 이 중에서 5개가 차트에 포함되도록 선택된 경우 하나의 애플리케이션 인스턴스와만 일치하는 필터를 적용하면 해당 애플리케이션 인스턴스만 테이블에 표시됩니다. 또한 이제 _선택한 앱_ 세트에 일치하는 애플리케이션만 포함되고 이에 따라 차트가 새로 고쳐집니다. 필터를 제거하면 10개의 모든 애플리케이션이 다시 테이블에 표시되고 _선택한 앱_ 세트가 모든 앱을 포함하도록 재설정됩니다.


## 셀
{: #usage_cells}

셀 페이지에는 두 개의 섹션이 있습니다.
1. 다음을 표시하는 세로 막대형 차트:
   * CFEE 인스턴스에서 사용할 수 있는 *총 사용 가능* 메모리 및 CPU
   * CFEE 인스턴스의 *모든 앱 인스턴스*에서 사용된 메모리 및 CPU
   * CFEE 인스턴스의 *선택한 앱 인스턴스*에서 사용된 메모리 및 CPU
   * 아래 테이블의 *시스템*에서 사용된 메모리 및 CPU. 시스템 사용량은 CFEE 서비스 컴포넌트와 애플리케이션 캐시에서 사용된 리소스의 합을 나타냅니다.

   모든 앱 인스턴스 또는 테이블에서 선택한 앱 인스턴스에서 사용된 메모리 또는 CPU의 백분율을 표시하려면 차트의 해당 부분 위로 마우스를 이동하십시오. 차트 막대 위로 마우스를 이동하면 사용 가능한 절대 메모리 또는 CPU, 모든 앱에서 사용된 메모리 또는 CPU 및 시스템+캐시에서 사용된 메모리 또는 CPU가 표시됩니다. 또한 총 사용 가능 메모리 또는 CPU에 대한 모든 앱과 시스템+캐시에서 사용된 메모리 또는 CPU의 백분율이 표시됩니다.

2. 모든 셀과 셀에서 실행 중인 애플리케이션 인스턴스를 나열하는 테이블. 테이블의 각 행에는 해당 셀 및 애플리케이션 인스턴스에 대한 리소스 정보가 표시됩니다.

  테이블의 첫 번째 열은 해당 애플리케이션 인스턴스가 페이지의 맨 위에 있는 차트에 포함될 *선택한 앱* 세트에 포함되는지 여부를 판별하는 선택란입니다. 애플리케이션 인스턴스를 선택한 세트에 포함(또는 제외)하려면 해당 선택란을 클릭하십시오. 애플리케이션 인스턴스를 세트에 포함하도록 선택하거나 선택 취소하면 그래프가 새로 고쳐집니다.

  다음 정보가 테이블에 열로 표시됩니다.
   * **셀 이름**: 셀의 이름입니다.
   * **애플리케이션 이름**: 셀에서 실행 중인 애플리케이션의 이름입니다. 사용자에게 애플리케이션에 액세스할 수 있는 권한이 없는 경우 대신 애플리케이션 GUID가 표시됩니다.
   * **인스턴스**: 셀에서 실행 중인 애플리케이션 인스턴스의 이름입니다.
   * **메모리-실제**: 셀에서 실행 중인 애플리케이션 인스턴스에서 사용되는 실제 메모리의 양(MB)입니다.
   * **메모리-예약됨**: 셀에서 실행 중인 애플리케이션 인스턴스에서 예약된 메모리의 양(MB)입니다.
   * **CPU(%)**: CFEE에서 사용 가능한 총 CPU 중에서 셀에서 실행 중인 애플리케이션 인스턴스에서 사용된 CPU의 백분율입니다.

### 셀 및 앱 인스턴스 필터링
테이블 위에 있는 **셀** 필터 드롭다운을 통해 테이블에 표시될 셀을 선택하여 테이블의 컨텐츠를 필터링할 수 있습니다.

또한 테이블 위의 필터 입력 필드를 사용하여 필터 필드에 입력하는 문자열과 일치하는 애플리케이션 인스턴스만 표시할 수 있습니다. 필터는 테이블 및 테이블 위의 차트 모두에 반영됩니다.

**참고:** 필터는 위의 차트에 포함된 _선택한 앱 인스턴스_ 세트에 포함하기 위해 첫 번째 열 테이블의 선택란을 통해 선택된 테이블 행과 독립적으로 작동합니다. 예를 들어, CFEE 환경에 총 10개의 애플리케이션 인스턴스가 있고 이 중에서 5개가 차트에 포함되도록 선택된 경우 하나의 애플리케이션 인스턴스와만 일치하는 필터를 적용하면 해당 애플리케이션 인스턴스만 테이블에 표시됩니다. 또한 이제 _선택한 앱 인스턴스_ 세트에 해당 앱 인스턴스만 포함되고 이에 따라 차트가 새로 고쳐집니다. 필터를 제거하면 10개의 모든 애플리케이션 인스턴스가 다시 테이블에 표시되고 _선택한 앱 인스턴스_ 세트가 모든 앱 인스턴스를 포함하도록 재설정됩니다.