---
title: Gerenciar definições de configuração do servidor de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Resumo: saiba como gerenciar as definições de configuração do servidor de conferência no Skype for Business Server.'
ms.openlocfilehash: c43734a2d79bf07023486eb163fff7bbef56e73f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818632"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Gerenciar definições de configuração do servidor de conferência no Skype for Business Server
 
**Resumo:** Saiba como gerenciar definições de configuração do servidor de conferência no Skype for Business Server.
  
Este tópico descreve como gerenciar definições de configuração de conferência. Para obter mais informações sobre como planejar e implantar a conferência, consulte [planejar conferências no Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [implantar conferências no Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
As configurações de conferência determinam itens como o tamanho máximo permitido para o conteúdo da reunião e folhetos; quantidade máxima de largura de banda para o serviço de conferência de compartilhamento de aplicativos; limites de armazenamento e períodos de expiração; as URLs dos downloads internos e externos do cliente compatível; ponteiros para URLs internas e externas em que os usuários podem obter ajuda e recursos de conferência; e as portas usadas para compartilhamento de aplicativos, áudio do cliente, transferências de arquivos e tráfego de mídia. Essas configurações permitem que você gerencie os servidores reais. Essas configurações podem ser definidas usando o Shell de gerenciamento do Skype for Business Server.
  
Quando você instala o Skype for Business Server, o sistema fornece uma única coleção de configurações de configuração de conferência (a coleção global). Se for necessário criar definições personalizadas para um site ou serviço, utilize o cmdlet **New-CsConferencingConfiguration**. Observe que as novas configurações podem ser aplicadas apenas no escopo do site ou do serviço; não é possível criar uma nova coleção global de definições de configuração de conferências, mas você pode modificar a coleção global usando o cmdlet **Set-CsConferencingConfiguration**. Além disso, nenhum site ou serviço pode hospedar mais de uma coleção de definições. Se você tentar criar novas definições para o site de Redmond e ele já hospedar uma coleção de definições de configuração de conferências, o comando falhará.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Gerenciar configurações de configuração de conferência usando o Shell de gerenciamento do Skype for Business Server

Para gerenciar as configurações de configuração de conferência usando o Shell de gerenciamento do Skype for Business Server, use os seguintes cmdlets:
  
**Definições de configuração de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as definições de configuração de conferência da organização.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção definições de configuração de conferência.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Remove o conjunto especificado de definições de configuração de conferência.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica um conjunto existente de definições de configuração de conferências.  <br/> |
   
O seguinte comando cria uma nova coleção de definições de configuração de conferência para o site Redmond (site:Redmond). Neste exemplo, foi incluído um parâmetro adicional (Organization), que é usado para definir o valor da propriedade Organization como Litwareinc: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Observe que você pode ter apenas uma coleção dessas por site, portanto, esse comando falhará se o site Redmond já tiver uma coleção de definições de configuração de conferência. 
  
O exemplo a seguir define uma nova coleção de definições de configuração de conferência, que é armazenada inicialmente na memória, e depois aplicada ao site Redmond. 
  
O primeiro comando no exemplo usa o cmdlet **New-CsConferencingConfiguration** para criar, em memória, uma nova coleção de definições armazenadas na variável $x. O parâmetro InMemory especifica que a coleção deve ser criada na memória, em vez de ser imediatamente aplicada ao site de Redmond.
  
Depois que a coleção tiver sido criada, o segundo comando define o valor da propriedade Organization como Litwareinc. 
  
Finalmente, o terceiro comando usa o cmdlet **Set-CsConferencingConfiguration** para aplicar realmente as novas configurações ao site Redmond:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Se você não chamar o cmdlet **Set-CsConferencingConfiguration**, as novas configurações nunca terão efeito. Em vez disso, elas desaparecerão assim que você terminar a sessão do Windows PowerShell ou excluir a variável $x.
  

