---
title: Gerenciar definições de configuração do servidor de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Resumo: Saiba como gerenciar as definições de configuração do servidor de conferência no Skype for Business Server.'
ms.openlocfilehash: 7f8714a4098285e955b559b2baf70d74957159a1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828281"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Gerenciar definições de configuração do servidor de conferência no Skype for Business Server
 
**Resumo:** Saiba como gerenciar as definições de configuração do servidor de conferência no Skype for Business Server.
  
Este tópico descreve como gerenciar as definições de configuração de conferências. Para obter mais informações sobre como planejar e implantar conferências, consulte [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
As definições de configuração de conferência determinam coisas como o tamanho máximo permitido para conteúdo e apostilas de reunião; quantidade máxima de largura de banda para o serviço conferência de compartilhamento de aplicativos; limites de armazenamento e períodos de expiração; as URLs para downloads internos e externos do cliente suportado; ponteiros para URLs internas e externas onde os usuários podem obter ajuda e recursos de conferência; e as portas usadas para compartilhamento de aplicativos, áudio do cliente, transferências de arquivos e tráfego de mídia. Essas configurações permitem que você gerencie os servidores reais por conta própria. Essas configurações podem ser definidas usando o Shell de Gerenciamento do Skype for Business Server.
  
Quando você instala o Skype for Business Server, o sistema fornece uma única coleção de definições de configuração de conferências (o conjunto global). Se precisar criar definições personalizadas para um site ou serviço, utilize o cmdlet **New-CsConferencingConfiguration**. Observe que novas configurações podem ser aplicadas apenas no escopo do site ou do serviço; não é possível criar uma nova coleção global de definições de configuração de conferências, mas é possível modificar a coleção global usando o cmdlet **Set-CsConferencingConfiguration.** Além disso, nenhum site ou serviço pode hospedar mais de uma coleção de definições. Se você tentar criar novas definições para o site de Redmond e ele já hospedar uma coleção de definições de configuração de conferências, o comando falhará.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Gerenciar definições de configuração de conferência usando o Shell de Gerenciamento do Skype for Business Server

Para gerenciar as definições de configuração de conferência usando o Shell de Gerenciamento do Skype for Business Server, use os seguintes cmdlets:
  
**Definições de configuração de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as definições de configuração de conferência para sua organização.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de definições de configuração de conferências.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Remove a coleção especificada de definições de configuração de conferências.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica um conjunto existente de definições de configuração de conferências.  <br/> |
   
O comando a seguir cria uma nova coleção de definições de configuração de conferência para o site Redmond (site:Redmond). Neste exemplo, um parâmetro adicional é incluído (Organization), que é usado para definir o valor da propriedade Organization como Litwareinc: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Observe que você pode ter apenas uma coleção desse tipo por site, portanto, esse comando falhará se o site Redmond já tiver uma coleção de definições de configuração de conferências. 
  
O próximo exemplo define uma nova coleção de definições de configuração de conferências, que são armazenadas na memória inicialmente e, em seguida, aplicadas ao site Redmond posteriormente. 
  
O primeiro comando usa o cmdlet **New-CsConferencingConfiguration** para criar uma nova coleção, na memória, de configurações armazenadas na variável $x. O parâmetro InMemory especifica que a coleção deve ser criada na memória, em vez de ser imediatamente aplicada ao site Redmond.
  
Depois que a coleção tiver sido criada, o segundo comando define o valor da propriedade Organization como Litwareinc. 
  
Finalmente, o terceiro comando usa o cmdlet **Set-CsConferencingConfiguration** para realmente aplicar as novas configurações ao site Redmond:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Se você não chamar o cmdlet **Set-CsConferencingConfiguration,** as novas configurações nunca terão efeito. Em vez disso, eles desaparecerão assim que você encerrar a sessão do Windows PowerShell ou excluir a variável $x.
  

