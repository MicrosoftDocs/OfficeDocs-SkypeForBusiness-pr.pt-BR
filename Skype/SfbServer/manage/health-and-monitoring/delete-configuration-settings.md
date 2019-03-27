---
title: Excluir um conjunto existente de definições de configuração de CDR em Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Resumo: Saiba como remover as definições de configuração de CDR em Skype para Business Server.'
ms.openlocfilehash: 470aade77fce211ba771c628b913efa4376a4a6f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873074"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Excluir um conjunto existente de definições de configuração de CDR em Skype para Business Server
 
**Resumo:** Saiba como remover as definições de configuração de CDR em Skype para Business Server.
  
O registro de detalhes das chamadas (CDR) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.
  
Quando você instala o Skype para Business Server, uma única coleção global de definições de configuração de CDR é criada para você. Os administradores têm a opção de criar coleções de definições personalizadas que podem ser aplicadas a sites individuais. Através do design, as definições configuradas no escopo do site têm precedência sobre aquelas no escopo global. Se você excluir as definições no escopo do site, então o CDR será gerenciado nesse site usando as definições globais.
  
Observe que você também pode "excluir" as definições globais. No entanto, as definições globais não serão realmente removidas. Em vez disso, todas as propriedades nessa coleção serão redefinidas para os valores padrão. Por exemplo, como padrão, a limpeza está ativada em uma coleção de definições de configuração de CDR. Suponha que você modifique a coleção global de forma que a limpeza seja desativada. Se você excluir as definições globais mais tarde, todas as propriedades serão redefinidas para seus valores padrão. Neste caso, isso significa que a limpeza será novamente ativada.
  
Você pode remover as definições de configuração de CDR usando o Skype para painel de controle do Business Server ou o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Para remover as definições de configuração de CDR com Skype para painel de controle do servidor de negócios

1. No painel de controle do servidor de negócios do Skype, clique em **monitoramento e arquivamento**. 
    
2. Na guia **Registro de Detalhes de Chamada**, selecione a coleção (ou coleções) de definições de CDR a ser removida. Para selecionar várias coleções, clique na primeira coleção, mantenha pressionada a tecla CTRL e clique em mais coleções.
    
3. Clique em **Editar** e então em **Excluir**.
    
4. No Skype para caixa de diálogo Painel de controle do Business Server, clique em **Okey**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo definições de configuração de CDR usando Cmdlets do Windows PowerShell

Você pode excluir um registro de definições de configuração usando o Windows PowerShell e o cmdlet **Remove-CsCdrConfiguration** de detalhes de chamada. Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Para remover uma coleção especificada das definições de configuração de CDR

 Este comando remove as definições de configuração de CDR aplicadas ao site da Redmond:
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração de CDR aplicadas ao escopo do site

 Este comando remove todas as definições de configuração de CDR aplicadas ao escopo do site:
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para remover todas as definições de configuração de CDR que desativam a gravação de detalhes de chamada

 Este comando remove todas as definições de configuração de CDR onde a gravação de detalhes de chamada foi desativada:
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Consulte Também

[Limpar manualmente o registro de detalhes da chamada e bancos de dados de qualidade da experiência no Skype para Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

