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
localization_priority: Normal
ms.collection: ''
description: Instruções para configurar o Conector de Dados de Chamada, que permite que a telemetria do Skype for Business local seja visualizada usando as ferramentas do Skype for Business Online.
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726921"
---
# <a name="configure-call-data-connector"></a>Configurar o Conector de Dados de Chamada

Este artigo descreve como configurar o Call Data Connector , um único conjunto de ferramentas que permite a exibição de Dados de Qualidade de Chamada do Skype for Business Server usando as ferramentas CQD (Painel de Qualidade de Chamadas) e Análise de Chamadas (CA) do Skype for Business Online.

Para obter mais informações sobre os benefícios e pré-requisitos do Conector de Dados de [Chamada,](plan-call-data-connector.md)como requisitos de função e configuração da conectividade híbrida, consulte Plan Call Data Connector .

## <a name="enable-monitoring"></a>Habilitar Monitoramento
 
Você deve configurar a coleta de dados de Registro de Dados de Chamada (CDR) e Qualidade da Experiência (QoE) em seu pool de front-end Monitoramento, com bancos de dados LCSCdr e QoEMetrics locais; Caso contrário, os Painéis de Qualidade de Chamada e Análise de Chamada não obterão dados para trabalhar. Antes de configurar o Conector de Dados de Chamada, siga as etapas fornecidas em Implantar monitoramento no [Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar CDR e QoE, bem como monitoramento básico.

> [!IMPORTANT]
> O Conector de Dados de Chamada não funcionará se o Monitoramento não estiver habilitado no pool de front-end.

## <a name="enable-call-data-connector"></a>Habilitar o Conector de Dados de Chamada

Para configurar e habilitar o Conector de Dados de Chamada, você usará os seguintes cmdlets:

| Cmdlet| Descrição|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Um cmdlet online que estabelece um coletor de dados online.|
| Get-CsCloudCallDataConnection | Um cmdlet online que recupera um coletor de dados online existente.|  
| Get-CsCloudCallDataConnector | Um cmdlet local que recupera as informações de conexão criadas pelo New-CsCloudCallDataConnection cmdlet. |
| Set-CsCloudCallDataConnector | Um cmdlet local que salva uma cópia local das informações de conexão criadas pelo New-CsCloudCallDataConnection cmdlet. |  
| Set-CsCloudCallDataConnectorConfiguration | Um cmdlet local que permite habilitar ou desabilitar o conector e personalizar o nível de escopo.|

> [!NOTE]
> Para apagar sua configuração e recomeçar, use o cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurar seu ambiente 

Para configurar seu ambiente para habilitar um coletor de dados online, você deve primeiro entrar no PowerShell do Skype for Business Online como administrador. Para saber mais, confira [Gerenciar o Skype for Business Online com o Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Há dois métodos para entrar no PowerShell do Skype for Business Online:

- Do shell de gerenciamento do Skype for Business Server 2019 (método recomendado)
- De outra sessão do PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Entre no PowerShell do Skype for Business Online a partir do shell de gerenciamento do Skype for Business Server (método recomendado)

1. Se estiver habilitando o conector pela primeira vez, execute o seguinte comando:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Se você receber um erro de que a conexão já existe, isso significa que a conexão de dados de chamada já existe para seu locatário. Nesse caso, execute o comando: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Faça logon no PowerShell do Skype for Business Online a partir de outra sessão do PowerShell (método opcional)

1.  Se estiver habilitando o conector pela primeira vez, execute o seguinte comando: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Se você receber um erro de que a conexão já existe, isso significa que a conexão de dados de chamada já existe para seu locatário. Nesse caso, execute o comando: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

A saída dos comandos acima contém um valor de token, que você precisará ao configurar seu ambiente local da seguinte forma:

No shell de gerenciamento do Skype for Business Server, especifique o seguinte comando:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurar o escopo

Você pode habilitar o Conector de Dados de Chamada para um site específico ou para toda a sua implantação do Skype for Business Server usando o cmdlet Set-CsCloudCallDataConnectorConfiguration dentro do shell de gerenciamento do Skype for Business Server. Por exemplo, o seguinte comando habilita o Conector de Dados de Chamada no escopo global:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Além das configurações globais, as definições de configuração do Conector de Dados de Chamada podem ser atribuídas ao escopo do site. Isso oferece flexibilidade de gerenciamento adicional quando se trata de monitoramento. Por exemplo, um administrador pode habilitar o encaminhamento do Conector de Dados de Chamada para o site Redmond, mas desabilitar o encaminhamento do Conector de Dados de Chamada para o site Dublin, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global. Por exemplo, suponha que o encaminhamento do Conector de Dados de Chamada está habilitado no escopo global, mas desabilitado no escopo do site (para o site Redmond). Isso significa que o registro de detalhes das chamada e as informações de QoE não serão encaminhadas para usuários no site redmond. No entanto, os usuários em outros sites (ou seja, usuários gerenciados pelas configurações globais em vez das configurações de site Redmond) terão seu registro de detalhes de chamada e informações de QoE encaminhadas.

Os valores das configurações mais usadas pelo Conector de Dados de Chamada são mostrados na tabela a seguir:  

|Propriedade|Descrição|Valor padrão|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica se o Conector de Dados de Chamada está habilitado. Se for True, os registros de monitoramento serão encaminhados para monitoramento online.  <br/> |$False  <br/> |
| Identidade | Determina o nível de escopo do comando: global ou site.   | global  |

## <a name="disable-call-data-connector"></a>Desabilitar o Conector de Dados de Chamada

Desabilitar o Conector de Dados de Chamada não desassocia o armazenamento de monitoramento do pool de Front-End, nem desinstala ou afeta o banco de dados de monitoramento de back-end. Quando você desabilita o Conector de Dados de Chamada, impede que o Skype for Business Server carregue dados de chamadas para a nuvem. 

Desabilite o Conector de Dados de Chamada usando o cmdlet Set-CsCloudCallDataConnectorConfiguration dentro do shell de gerenciamento do Skype for Business Server. Por exemplo, o seguinte comando desabilita o Conector de Dados de Chamada no escopo global definindo a propriedade EnableCallDataConnector como $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Se você deseja retomar o carregamento de dados de chamada para a nuvem, de definida a propriedade EnableCallDataConnector de volta para $True, conforme mostrado no exemplo a seguir:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Exibir dados locais por meio do painel online

 Depois que o Conector de Dados de Chamada está habilitado, você pode exibir seus dados de chamada local no painel Análise de Chamadas ou no Painel de Qualidade de Chamadas, conforme descrito em [Usar](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) Análise de Chamadas para solucionar problemas de baixa qualidade e ativar e usar o Painel de Qualidade de Chamadas para o Microsoft Teams e [o Skype for Business Online.](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)

## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre os cmdlets, você pode usar o comando Get-Help do Shell de Gerenciamento do Skype for Business Server. Por exemplo:

Get-Help Get-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnectorConfiguration | more
