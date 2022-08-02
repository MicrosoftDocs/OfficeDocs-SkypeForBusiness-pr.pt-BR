---
title: Configurar o Conector de Dados de Chamada
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Instruções para configurar o Conector de Dados de Chamada, que permite que a telemetria de Skype for Business local seja exibida usando Skype for Business online.
ms.openlocfilehash: 0d92d31798cd4b3fb5a1b4c555ff0ff00c2bdf31
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156929"
---
# <a name="configure-call-data-connector"></a>Configurar o Conector de Dados de Chamada

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Este artigo descreve como configurar o Conector de Dados de Chamada – um único conjunto de ferramentas que permite a exibição de dados de qualidade de chamada Skype for Business Server usando ferramentas do CQD (Painel de Qualidade de Chamadas) da Microsoft e da AC (Análise de Chamadas).

Para obter mais informações sobre os benefícios e os pré-requisitos do Conector de Dados de Chamada, como requisitos de função e configuração de conectividade híbrida, consulte [Plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Habilitar Monitoramento
 
Você deve configurar a cdr (gravação de dados de chamada) e a coleta de dados de qualidade de experiência (QoE) no monitoramento do pool de front-end com bancos de dados LCSCdr e QoEMetrics locais; caso contrário, os Painéis de Qualidade de Chamada e Análise de Chamadas não obterão dados para trabalhar. Antes de configurar o Conector de Dados de Chamada, siga as etapas fornecidas em Implantar monitoramento no [Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar o CDR e o QoE, bem como o monitoramento básico.

> [!IMPORTANT]
> O Conector de Dados de Chamada não funcionará se o Monitoramento não estiver habilitado no pool de front-end.

## <a name="enable-call-data-connector"></a>Habilitar Conector de Dados de Chamada

Para configurar e habilitar o Conector de Dados de Chamada, você usará os seguintes cmdlets:

| Cmdlet| Descrição|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Um cmdlet online que estabelece um coletor de dados online.|
| Get-CsCloudCallDataConnection | Um cmdlet online que recupera um coletor de dados online existente.|  
| Get-CsCloudCallDataConnector | Um cmdlet local que recupera as informações de conexão criadas pelo New-CsCloudCallDataConnection cmdlet. |
| Set-CsCloudCallDataConnector | Um cmdlet local que salva uma cópia local das informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection local. |  
| Set-CsCloudCallDataConnectorConfiguration | Um cmdlet local que permite habilitar ou desabilitar o conector e personalizar o nível de escopo.|

> [!NOTE]
> Para apagar sua configuração e recomeçar, use o cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurar seu ambiente 

Para configurar seu ambiente para habilitar um coletor de dados online, você deve primeiro fazer logon no módulo do PowerShell do Microsoft Teams como administrador. Para obter mais informações, consulte [Visão geral do Microsoft Teams PowerShell](/microsoftteams/teams-powershell-overview).

Há dois métodos para fazer logon no módulo do PowerShell do Microsoft Teams:

- Do shell de Skype for Business Server 2019 (método recomendado)
- De outra sessão do PowerShell

#### <a name="log-in-to-microsoft-teams-powershell-module-from-the-skype-for-business-server-management-shell-recommended-method"></a>Faça logon no módulo do PowerShell do Microsoft Teams no shell Skype for Business Server de gerenciamento (método recomendado)

1. Se estiver habilitando o conector pela primeira vez, execute o seguinte comando:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Se você receber um erro indicando que a conexão já existe, isso significa que a conexão de dados de chamada já existe para seu locatário. Nesse caso, execute o comando: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-microsoft-teams-powershell-module-from-another-powershell-session-optional-method"></a>Fazer logon no módulo do PowerShell do Microsoft Teams de outra sessão do PowerShell (método opcional)

1.  Se estiver habilitando o conector pela primeira vez, execute o seguinte comando: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Se você receber um erro indicando que a conexão já existe, isso significa que a conexão de dados de chamada já existe para seu locatário. Nesse caso, execute o comando: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

A saída dos comandos acima contém um valor de token, que você precisará ao configurar seu ambiente local da seguinte maneira:

No shell de Skype for Business Server, especifique o seguinte comando:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configure o escopo

Você pode habilitar o Conector de Dados de Chamada para um site específico ou para toda Skype for Business Server implantação usando o cmdlet Set-CsCloudCallDataConnectorConfiguration de dentro do shell de gerenciamento Skype for Business Server. Por exemplo, o comando a seguir habilita o Conector de Dados de Chamada no escopo global:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Além das configurações globais, as definições de configuração do Conector de Dados de Chamada podem ser atribuídas ao escopo do site. Isso fornece flexibilidade de gerenciamento adicional quando se trata de monitoramento. Por exemplo, um administrador pode habilitar o encaminhamento do Conector de Dados de Chamada para o site redmond, mas desabilitar o encaminhamento do Conector de Dados de Chamada para o site de Dublin, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global. Por exemplo, suponha que o encaminhamento do Conector de Dados de Chamada esteja habilitado no escopo global, mas desabilitado no escopo do site (para o site redmond). Isso significa que a gravação de detalhes da chamada e as informações de QoE não serão encaminhadas para os usuários no site redmond. No entanto, os usuários em outros sites (ou seja, usuários gerenciados pelas configurações globais em vez das configurações do site de Redmond) terão suas informações de QoE e gravação de detalhes de chamada encaminhadas.

Os valores para as configurações mais usadas pelo Conector de Dados de Chamada são mostrados na tabela a seguir:  

|Propriedade|Descrição|Valor padrão|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica se o Conector de Dados de Chamada está habilitado. Se For True, os registros de monitoramento serão encaminhados para o monitoramento online.  <br/> |$False  <br/> |
| Identidade | Determina o nível de escopo do comando: global ou site.   | global  |

## <a name="disable-call-data-connector"></a>Desabilitar o Conector de Dados de Chamada

Desabilitar o Conector de Dados de Chamada não desassocia o repositório de monitoramento do pool de Front-Ends, nem desinstala ou afeta o banco de dados de monitoramento de back-end. Ao desabilitar o Conector de Dados de Chamada, você Skype for Business Server de carregar dados de chamada para a nuvem. 

Desabilite o Conector de Dados de Chamada usando Set-CsCloudCallDataConnectorConfiguration cmdlet de dentro do shell Skype for Business Server gerenciamento. Por exemplo, o comando a seguir desabilita o Conector de Dados de Chamada no escopo global definindo a propriedade EnableCallDataConnector como $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Se você quiser retomar o carregamento de dados de chamada para a nuvem, defina a propriedade EnableCallDataConnector de volta para $True, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Exibir dados locais por meio do painel online

 Depois que o Conector de Dados de Chamada estiver habilitado, você poderá exibir seus dados de chamada locais no painel do Call Analytics ou no Painel de Qualidade de Chamadas, conforme descrito em [Usar](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) Análise de Chamadas para solucionar problemas de baixa qualidade e ativar e usar o Painel de Qualidade de Chamadas para [o Microsoft Teams e o Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre os cmdlets, você pode usar o comando Get-Help do shell de Skype for Business Server Management. Por exemplo:

Get-Help Get-CsCloudCallDataConnector | mais

Get-Help Set-CsCloudCallDataConnector | mais

Get-Help Set-CsCloudCallDataConnectorConfiguration | mais
