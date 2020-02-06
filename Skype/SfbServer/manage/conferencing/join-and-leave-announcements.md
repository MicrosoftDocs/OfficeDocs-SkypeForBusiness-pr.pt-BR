---
title: Gerenciar o ingresso em conferência e deixar comunicados no Skype for Business Server
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
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Resumo: saiba como gerenciar o ingresso em conferência e deixar comunicados no Skype for Business Server.'
ms.openlocfilehash: 5f975637ca1d85e11c6889a07ff90055ef79ffc5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818542"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Gerenciar o ingresso em conferência e deixar comunicados no Skype for Business Server
 
**Resumo:** Saiba como gerenciar o ingresso em conferência e deixar comunicados no Skype for Business Server.
  
Quando os usuários de discagem entram ou deixam uma conferência, o aplicativo de anúncio de conferência pode anunciar a entrada ou a saída tocando um tom ou dizendo seus nomes. Você pode alterar a forma como os comunicados funcionam usando o Shell de gerenciamento do Skype for Business Server e o cmdlet **set-CsDialinConferencing** com os seguintes parâmetros:
  
- EnableNameRecording  - Determina se os participantes anônimos devem receber uma solicitação para registrar seus nomes antes de entrar na conferência. O valor padrão é "$true", que significa que os participantes receberão essa solicitação. (Os participantes autenticados não registram seus nomes porque seu nome de exibição é utilizado.)
    
- EntryExitAnnouncementsEnabledByDefault - Indica se os anúncios estão ativados ou desativados por padrão. O valor padrão é "$false", o que significa que, por padrão, não há anúncios quando os participantes participam ou saem de uma conferência. O organizador da reunião pode substituir essa configuração ao agendar uma reunião.
    
- EntryExitAnnouncementsType - Indica a ação a ser executada sempre que um participante participa ou sai de uma conferência para a qual os anúncios estão habilitados. O valor padrão é "UseNames", que significa que há um anúncio parecido com o seguinte: "Ken Myer está participando da conferência" quando os anúncios são ativados.
    
É possível definir essas configurações no escopo global ou no escopo do site. As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Para modificar o comportamento de anúncio de ingresso e saída de conferência

1. Faça logon no computador como membro do grupo  RTCUniversalServerAdmins  ou como membro da função  Cs-ServerAdministrator  ou  CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute o seguinte no prompt de comando:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Esse cmdlet recupera informações sobre a necessidade de os participantes gravarem o nome ao ingressar em uma conferência e como o Skype for Business Server responde quando os participantes se unem ou deixam uma conferência discada.
    
4. Execute o seguinte no prompt de comando:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

Neste exemplo, as configurações estão definidas no escopo do site para Redmond. Os anúncios estão ativados, mas os participantes não recebem uma solicitação para inserir seus nomes quando ingressam em uma conferência. Um tom é reproduzido quando os participantes entram e saem de uma conferência.
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Para obter mais informações, incluindo a sintaxe e uma lista completa de parâmetros, consulte [set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

