---
title: Configurar o conector de dados de chamada
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para configurar o conector de dados da chamada, que permite a telemetria do Skype para negócios local para ser exibidos usando o Skype para as ferramentas de Business Online.
ms.openlocfilehash: 959bb182da91029fd43ebc3ccb99fb5a69d820b2
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838820"
---
# <a name="configure-call-data-connector"></a>Configurar o conector de dados de chamada

Este artigo descreve como configurar o conector de dados chamada – um único conjunto de ferramentas que permite a exibição Skype para dados de qualidade de chamada do Business Server usando Skype para ferramentas de negócios Online chamada qualidade Dashboard (CQD) e análise de chamada (CA). 

> [!NOTE]
> Nesta versão de demonstração pública, painel de análise de chamadas somente está disponível.

Para obter mais informações sobre os benefícios de conector de dados de chamadas e pré-requisitos, como requisitos de função e configurar a conectividade híbrida, consulte [Planejar conector de dados da chamada](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Habilitar o monitoramento
 
Você deve configurar o registro de dados de chamadas (CDR) e coleta de dados Quality of Experience (QoE) em seu front-end do pool de monitoramento, com LCSCdr e QoEMetrics bancos de dados locais; Caso contrário, a análise de chamada e os painéis de qualidade de chamada não obterá dados para trabalhar. Antes, você configurar conector de dados de chamada, siga as etapas fornecidas em [Deploy monitoramento no Skype para Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar tanto CDR e QoE como monitoramento básico.

> [!IMPORTANT]
> Conector de dados de chamada não funcionará se monitoramento não estiver habilitado no pool de front-end.

## <a name="enable-call-data-connector"></a>Habilitar o conector de dados de chamada

Para configurar e habilitar o conector de dados da chamada, você usará os cmdlets a seguir:

| Cmdlet| Descrição|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Um cmdlet online que estabelece o coletor de dados online.|
| Get-CsCloudCallDataConnection | Um cmdlet online que recupera o coletor de dados de online existente.|  
| Get-CsCloudCallDataConnector | Um cmdlet no local que recupera as informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Um cmdlet no local que salva uma cópia local das informações de conexão criadas pelo cmdlet New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Um cmdlet no local que permite ativar ou desativar o conector e personalizar o nível de escopo.|

### <a name="configure-your-environment"></a>Configurar seu ambiente 

Para configurar o ambiente para permitir o coletor de dados online, você deve primeiro faça logon no Skype para negócios Online PowerShell como administrador. Para obter mais informações, consulte [Gerenciar Skype para negócios Online com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Há dois métodos para fazer logon no Skype para negócios Online PowerShell:

- Do Skype do shell de gerenciamento do Business Server 2019 (recomendado método)
- A partir de outra sessão do PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Faça logon no Skype para negócios Online PowerShell do Skype do shell de gerenciamento do Business Server (recomendado método)

1. Se habilitar o conector pela primeira vez, execute o seguinte comando:

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Se você receber um erro dizendo que a conexão já existe, isso significa que a conexão de dados chamada já existe para seu locatário. Nesse caso, execute o comando: 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Faça logon no Skype para negócios Online PowerShell a partir de outra sessão PowerShell (método opcional)

1.  Se habilitar o conector pela primeira vez, execute o seguinte comando: 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  Se você receber um erro dizendo que a conexão já existe, isso significa que a conexão de dados chamada já existe para seu locatário. Nesse caso, execute o comando: 

    ```
    Get-CsCloudCallDataConnection  
    ```

A saída dos comandos acima contém um valor de token, você precisará configurar seu ambiente local da seguinte maneira:

De dentro do Skype do shell de gerenciamento do Business Server, especifique o seguinte comando:

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurar o escopo

Você pode habilitar o conector de dados da chamada para um site específico ou para seu Skype inteira para implantação de servidor de negócios usando o cmdlet Set-CsCloudCallDataConnectorConfiguration do dentro do Skype do shell de gerenciamento do servidor de negócios. Por exemplo, o comando a seguir habilita a chamar o conector de dados no escopo global:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Além das definições globais, as definições de configuração do conector de dados de chamada podem ser atribuídas ao escopo do site. Isso oferece flexibilidade de gerenciamento adicionais quando se trata de monitoramento. Por exemplo, um administrador pode ativar o encaminhamento de chamadas de conector de dados para o site Redmond, mas desativar o encaminhamento de chamadas de conector de dados para o site de Dublin, conforme mostrado no exemplo a seguir:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global. Por exemplo, suponha que o encaminhamento de chamadas de conector de dados é habilitado no escopo global, mas desabilitado no escopo do site (para o site de Redmond). Isso significa que chamar o registro de detalhes e informações de QoE não será encaminhada para os usuários no site de Redmond. No entanto, os usuários em outros sites (ou seja, usuários gerenciados pelas definições globais, em vez de configurações do site de Redmond) terão suas informações de QoE encaminhadas e o registro de detalhes da chamada.

Valores para as configurações mais comumente usadas usados pelo conector de dados da chamada são mostrados na tabela a seguir:  

|Propriedade|Descrição|Valor padrão|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica se o conector de dados de chamadas está habilitado. Se for True, o monitoramento de registros será encaminhada para monitoramento online.  <br/> |$False  <br/> |
| Identidade  | Determina o nível de escopo para o comando: global ou site.   | global  |

## <a name="disable-call-data-connector"></a>Desabilitar o conector de dados de chamada

Desabilitar o conector de dados de chamada não desassociar o repositório de monitoramento do pool de Front-End, nem desinstalar ou caso contrário afetar o banco de dados de monitoramento de back-end. Quando você desabilita o conector de dados da chamada, pare Skype para Business Server de carregar dados de chamada para a nuvem. 

Desabilitar o conector de dados de chamada usando o cmdlet Set-CsCloudCallDataConnectorConfiguration do dentro do Skype do shell de gerenciamento do servidor de negócios. Por exemplo, o comando a seguir desabilita o conector de dados chamada no escopo global, definindo a propriedade EnableCallDataConnector como $False:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Se você deseja continuar com o carregamento de dados de chamada para a nuvem, defina a propriedade de EnableCallDataConnector voltar ao $True, conforme mostrado no exemplo a seguir:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Modo de exibição de dados por meio do painel online no local

 Depois de chamar o conector de dados estiver habilitado, você pode exibir os dados de chamada local no painel de análise de chamadas, conforme descrito na [Análise de uso de chamadas para solucionar problemas de baixa qualidade](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).


## <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre os cmdlets, você pode usar o comando Get-Help do Skype do Shell de gerenciamento do servidor de negócios. Por exemplo:

Get-Help Get-CsCloudCallDataConnector | mais

Get-Help Set-CsCloudCallDataConnector | mais

Get-Help Set-CsCloudCallDataConnectorConfiguration | mais