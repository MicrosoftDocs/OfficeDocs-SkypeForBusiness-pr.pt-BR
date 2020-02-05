---
title: Configurar o Call data Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para configurar o Call data Connector, que permite que a telemetria do Skype for Business local seja exibida usando as ferramentas do Skype for Business online.
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726921"
---
# <a name="configure-call-data-connector"></a>Configurar o Call data Connector

Este artigo descreve como configurar o Call data Connector – um único conjunto de ferramentas que permite exibir dados de qualidade de chamada do Skype for Business Server usando o painel de qualidade de chamada do Skype for Business online (CQD) e as ferramentas de análise de chamada (CA).

Para obter mais informações sobre os benefícios e pré-requisitos do Call data Connector, como requisitos de função e configuração da conectividade híbrida, consulte [Plan Call data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Habilitar o monitoramento
 
Você deve configurar o registro de dados de chamada (CDR) e a coleta de dados de QoE (qualidade da experiência) em seu monitoramento do pool de front-ends, com bancos de dados locais do LCSCdr e do QoEMetrics; caso contrário, os painéis de análise de chamada e de qualidade de chamada não terão dados com os quais trabalhar. Antes de configurar o Call data Connector, siga as etapas fornecidas em [Deploy Monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar CDR e QoE, bem como monitoramento básico.

> [!IMPORTANT]
> Call data Connector não funcionará se o monitoramento não estiver habilitado no pool de front-ends.

## <a name="enable-call-data-connector"></a>Habilitar conector de dados de chamada

Para configurar e habilitar o Call data Connector, você usará os seguintes cmdlets:

| Cmdlet| Descrição|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Um cmdlet online que estabelece um coletor de dados online.|
| Get-CsCloudCallDataConnection | Um cmdlet online que recupera um coletor de dados online existente.|  
| Get-CsCloudCallDataConnector | Um cmdlet local que recupera as informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Um cmdlet local que salva uma cópia local das informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Um cmdlet local que permite habilitar ou desabilitar o conector e personalizar o nível de escopo.|

> [!NOTE]
> Para apagar sua configuração e começar novamente, use o cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurar seu ambiente 

Para configurar seu ambiente para habilitar um coletor de dados online, primeiro você deve fazer logon no Skype for Business online PowerShell como administrador. Para obter mais informações, consulte [Manage Skype for Business online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Há dois métodos para fazer logon no Skype for Business online PowerShell:

- No Shell de gerenciamento do Skype for Business Server 2019 (método recomendado)
- De outra sessão do PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Faça logon no Skype for Business online PowerShell do Shell de gerenciamento do Skype for Business Server (método recomendado)

1. Se habilitar o conector pela primeira vez, execute o seguinte comando:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Se você receber um erro de que a conexão já existe, isso significa que a conexão de dados de chamada já existe para o locatário. Nesse caso, execute o comando: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Faça logon no Skype for Business online PowerShell a partir de outra sessão do PowerShell (método opcional)

1.  Se habilitar o conector pela primeira vez, execute o seguinte comando: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Se você receber um erro de que a conexão já existe, isso significa que a conexão de dados de chamada já existe para o locatário. Nesse caso, execute o comando: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

A saída dos comandos acima contém um valor de token, que você precisará ao configurar seu ambiente local da seguinte maneira:

No Shell de gerenciamento do Skype for Business Server, especifique o seguinte comando:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurar o escopo

Você pode habilitar o Call data Connector para um determinado site ou para toda a sua implantação do Skype for Business Server usando o cmdlet Set-CsCloudCallDataConnectorConfiguration de dentro do Shell de gerenciamento do Skype for Business Server. Por exemplo, o seguinte comando habilita o Call data Connector no escopo global:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Além das configurações globais, as definições de configuração do conector de dados de chamadas podem ser atribuídas ao escopo do site. Isso oferece flexibilidade de gerenciamento adicional quando se trata de monitoramento. Por exemplo, um administrador pode habilitar o encaminhamento do conector de dados de chamada para o site de Redmond, mas desabilitar o encaminhamento do conector de dados de chamadas para o site Dublin, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global. Por exemplo, suponha que o encaminhamento do Call data Connector está habilitado no escopo global, mas desabilitado no escopo do site (para o site de Redmond). Isso significa que a gravação de detalhes da chamada e as informações de QoE não serão encaminhadas para os usuários no site de Redmond. No entanto, os usuários em outros sites (ou seja, os usuários gerenciados pelas configurações globais em vez das configurações de site de Redmond) terão suas informações de registro de detalhes de chamadas e de QoE encaminhadas.

Os valores das configurações usadas com mais frequência usadas pelo Call data Connector são mostrados na tabela a seguir:  

|Propriedade|Descrição|Valor padrão|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica se o conector de dados de chamada está habilitado. Se true, os registros de monitoramento serão encaminhados para o monitoramento online.  <br/> |$False  <br/> |
| Identidade | Determina o nível de escopo para o comando: global ou site.   | global  |

## <a name="disable-call-data-connector"></a>Desabilitar o conector de dados de chamadas

Desabilitar o Call data Connector não desassocia o repositório de monitoramento do pool de front-ends, nem desinstala ou afeta o banco de dados de monitoramento de backend. Ao desabilitar o Call data Connector, você interrompe o Skype for Business Server de carregar dados de chamadas para a nuvem. 

Você desabilita o Call data Connector usando o cmdlet Set-CsCloudCallDataConnectorConfiguration de dentro do Shell de gerenciamento do Skype for Business Server. Por exemplo, o comando a seguir desabilita o conector de dados de chamada no escopo global, definindo a propriedade EnableCallDataConnector como $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Se você quiser continuar carregando dados de chamada para a nuvem, defina a propriedade EnableCallDataConnector de volta para $True, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Exibir dados locais por meio do painel online

 Após a habilitação do conector de dados de chamada, você pode exibir os dados de chamada local no painel do Analytics ou no painel de qualidade de chamada, conforme descrito em [usar o Call Analytics para solucionar problemas de qualidade ruim](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) e [ativar e usar o painel de qualidade da chamada para o Microsoft Teams e o Skype for Business online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre os cmdlets, você pode usar o comando Get-Help do Shell de gerenciamento do Skype for Business Server. Por exemplo:

Get-Help Get-CsCloudCallDataConnector | adicionais

Get-Help Set-CsCloudCallDataConnector | adicionais

Get-Help Set-CsCloudCallDataConnectorConfiguration | adicionais
