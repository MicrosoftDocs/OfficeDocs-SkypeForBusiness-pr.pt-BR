---
title: Gerenciar configurações do servidor de conferência no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Resumo: Saiba como gerenciar definições de configuração de servidor conferência no Skype para Business Server 2015.'
ms.openlocfilehash: 88c127acdd569945eddb41e997034e5ea23ea2a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server-2015"></a>Gerenciar configurações do servidor de conferência no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar definições de configuração de servidor conferência no Skype para Business Server 2015.
  
Este tópico descreve como gerenciar definições de configuração de conferência. Para obter mais informações sobre como planejar e implantar a conferência, consulte [Plan para conferências no Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferência no Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Definições de configuração de conferência determinam coisas como o tamanho máximo permitido para o conteúdo das reuniões e folhetos; quantidade máxima de largura de banda para o serviço de conferência de compartilhamento de aplicativo; limites de armazenamento e períodos de expiração; as URLs internas e externas downloads do cliente com suporte; ponteiros para URLs internas e externas, onde os usuários podem obter ajuda de conferência e recursos; e as portas usadas para compartilhamento de aplicativos, áudio do cliente, transferências de arquivos e tráfego de mídia. Essas configurações permitem que você gerencie os servidores reais. Essas configurações podem ser definidas usando Skype do Shell de gerenciamento do servidor de negócios.
  
Quando você instala o Skype para Business Server, o sistema fornece uma única coleção de conferência (a coleção global) de definições de configuração. Se for necessário criar definições personalizadas para um site ou serviço, utilize o cmdlet **New-CsConferencingConfiguration**. Observe que as novas configurações podem ser aplicadas apenas no escopo do site ou do serviço; não é possível criar uma nova coleção global de definições de configuração de conferências, mas você pode modificar a coleção global usando o cmdlet **Set-CsConferencingConfiguration**. Além disso, nenhum site ou serviço pode hospedar mais de uma coleção de definições. Se você tentar criar novas definições para o site de Redmond e ele já hospedar uma coleção de definições de configuração de conferências, o comando falhará.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Gerenciar definições de configuração de conferência usando o Skype do Shell de gerenciamento do servidor de negócios

Para gerenciar definições de configuração de conferência usando Skype do Shell de gerenciamento do servidor de negócios, use os cmdlets a seguir:
  
**Definições de configuração de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as definições de configuração de conferência da organização.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção definições de configuração de conferência.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Remove o conjunto especificado de definições de configuração de conferência.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica um conjunto existente de definições de configuração de conferências.  <br/> |
   
O seguinte comando cria uma nova coleção de definições de configuração de conferência para o site Redmond (site:Redmond). Neste exemplo, foi incluído um parâmetro adicional (Organization), que é usado para definir o valor da propriedade Organization como Litwareinc: 
  
```
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc

```

Observe que você pode ter apenas uma coleção dessas por site, portanto, esse comando falhará se o site Redmond já tiver uma coleção de definições de configuração de conferência. 
  
O exemplo a seguir define uma nova coleção de definições de configuração de conferência, que é armazenada inicialmente na memória, e depois aplicada ao site Redmond. 
  
O primeiro comando no exemplo usa o cmdlet **New-CsConferencingConfiguration** para criar, em memória, uma nova coleção de definições armazenadas na variável $x. O parâmetro InMemory especifica que a coleção deve ser criada na memória, em vez de ser imediatamente aplicada ao site de Redmond.
  
Depois que a coleção tiver sido criada, o segundo comando define o valor da propriedade Organization como Litwareinc. 
  
Finalmente, o terceiro comando usa o cmdlet **Set-CsConferencingConfiguration** para aplicar realmente as novas configurações ao site Redmond:
  
```
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x

```

Se você não chamar o cmdlet **Set-CsConferencingConfiguration**, as novas configurações nunca terão efeito. Em vez disso, elas desaparecerão assim que você terminar a sessão do Windows PowerShell ou excluir a variável $x.
  

