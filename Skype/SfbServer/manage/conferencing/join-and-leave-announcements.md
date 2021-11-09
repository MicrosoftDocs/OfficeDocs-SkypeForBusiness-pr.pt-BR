---
title: Gerenciar comunicados de união e saída de conferências Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Resumo: saiba como gerenciar a junção de conferências e deixar anúncios no Skype for Business Server.'
ms.openlocfilehash: ee624ee347bb52f4bbdf4fbfae42f5303c8b6a54
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837663"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Gerenciar comunicados de união e saída de conferências Skype for Business Server
 
**Resumo:** Saiba como gerenciar a junção de conferências e deixar comunicados Skype for Business Server.
  
Quando os usuários discados inserem ou saem de uma conferência, os aplicativo Comunicado de Conferência podem anunciar sua entrada ou saída tocando um tom ou dizendo seus nomes. Você pode alterar como os anúncios funcionam usando o Shell de Gerenciamento Skype for Business Server **Set-CsDialinConferencing** com os seguintes parâmetros:
  
- EnableNameRecording - Determina se os participantes anônimos são solicitados a gravar seu nome antes de entrar na conferência. O valor padrão é "$true", que significa que os participantes receberão essa solicitação. (Os participantes autenticados não registram seus nomes, pois em vez disso exibem seus nomes de exibição.)
    
- EntryExitAnnouncementsEnabledByDefault - Indica se os anúncios estão ativas ou desligadas por padrão. O valor padrão é "$false", que significa que, por padrão, não anúncios quando os participantes ingressam ou saem de uma conferência. O organizador da reunião pode substituir essa configuração ao agendar uma reunião.
    
- EntryExitAnnouncementsType - Indica a ação tomada sempre que um participante insue ou saia de uma conferência para a qual os comunicados estão habilitados. O valor padrão é "UseNames", que significa que há um anúncio parecido com o seguinte: "Ken Myer ingressou na conferência" quando os anúncios estão ativados.
    
É possível definir essas configurações no escopo global ou no escopo do site. As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Para modificar o comportamento de anúncio de ingresso e saída de conferência

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função Cs-ServerAdministrator ou CsAdministrator.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
3. Execute o seguinte no prompt de comando:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Este cmdlet recupera informações sobre se os participantes devem gravar seu nome ao ingressar em uma conferência e como o Skype for Business Server responde quando os participantes inserem ou saem de uma conferência discada.
    
4. Execute o seguinte no prompt de comando:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

No exemplo a seguir, as configurações são configuradas no escopo do site para Redmond. Os anúncios estão ativados, mas os participantes não recebem uma solicitação para inserir seus nomes quando ingressam em uma conferência. Um tom é tocado quando os participantes entram ou saem de uma conferência:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Para obter mais informações, incluindo sintaxe e uma lista completa de parâmetros, consulte [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
