---
title: Gerenciar configurações do servidor de conferência em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Resumo: saiba como gerenciar as configurações do servidor de conferência em Skype for Business Server.'
ms.openlocfilehash: 14fed927e18d291cf17a5c00ee82dac7ef80a6d1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773701"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Gerenciar configurações do servidor de conferência em Skype for Business Server
 
**Resumo:** Saiba como gerenciar as configurações do servidor de conferência em Skype for Business Server.
  
Este tópico descreve como gerenciar as configurações de conferência. Para obter mais informações sobre como planejar e implantar conferências, consulte [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
As configurações de conferência determinam coisas como o tamanho máximo permitido para conteúdo de reunião e apostilas; quantidade máxima de largura de banda para o serviço de Conferência de Compartilhamento de Aplicativos; limites de armazenamento e períodos de expiração; as URLs para downloads internos e externos do cliente com suporte; ponteiros para URLs internas e externas onde os usuários podem obter ajuda e recursos de conferência; e as portas usadas para compartilhamento de aplicativos, áudio do cliente, transferências de arquivos e tráfego de mídia. Essas configurações permitem que você gerencie os servidores reais por conta própria. Essas configurações podem ser definidas usando Skype for Business Server Shell de Gerenciamento.
  
Ao instalar o Skype for Business Server, o sistema fornece uma única coleção de configurações de conferência (a coleção global). Se precisar criar definições personalizadas para um site ou serviço, utilize o cmdlet **New-CsConferencingConfiguration**. Observe que as novas configurações só podem ser aplicadas no escopo do site ou do serviço; não é possível criar uma nova coleção global de configurações de conferência, mas você pode modificar a coleção global usando o cmdlet **Set-CsConferencingConfiguration.** Além disso, nenhum site ou serviço pode hospedar mais de uma coleção de definições. Se você tentar criar novas definições para o site de Redmond e ele já hospedar uma coleção de definições de configuração de conferências, o comando falhará.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Gerenciar configurações de conferência usando o Shell de Gerenciamento Skype for Business Server Gerenciamento

Para gerenciar as configurações de conferência usando Skype for Business Server Shell de Gerenciamento, use os seguintes cmdlets:
  
**Configurações de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as configurações de conferência para sua organização.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de configurações de conferência.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Remove a coleção especificada de configurações de conferência.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica um conjunto existente de definições de configuração de conferências.  <br/> |
   
O comando a seguir cria uma nova coleção de configurações de conferência para o site redmond (site:Redmond). Neste exemplo, um parâmetro adicional é incluído (Organização) que é usado para definir o valor da propriedade Organization como Litwareinc: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Observe que você pode ter apenas um conjunto por site, para que esse comando falhe se o site Redmond já tiver uma coleção de configurações de conferência. 
  
O próximo exemplo define uma nova coleção de definições de configuração de conferência, que são armazenadas na memória inicialmente e aplicadas ao site redmond posteriormente. 
  
O primeiro comando usa o cmdlet **New-CsConferencingConfiguration** para criar uma nova coleção de configurações na memória armazenadas na variável $x. O parâmetro InMemory especifica que a coleção deve ser criada na memória em vez de ser aplicada imediatamente ao site redmond.
  
Após a criação da coleção, o segundo comando define o valor da propriedade Organization como Litwareinc. 
  
Por fim, o terceiro comando usa o cmdlet **Set-CsConferencingConfiguration** para realmente aplicar as novas configurações ao site redmond:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Se você não chamar o cmdlet **Set-CsConferencingConfiguration,** as novas configurações nunca terão efeito. Em vez disso, eles desaparecerão assim que você terminar sua sessão Windows PowerShell ou excluir a variável $x.
