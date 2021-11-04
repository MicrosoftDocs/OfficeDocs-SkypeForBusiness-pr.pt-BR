---
title: Publicar alterações pendentes na configuração de roteamento de voz Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Resumo: saiba como revisar, publicar ou cancelar alterações de configuração de roteamento de voz no Skype for Business Server usando o painel de controle Skype for Business Server de controle.'
ms.openlocfilehash: bf859dd7ed31a9a08fcba18af1b65cd1f34e8d16
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764849"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Publicar alterações pendentes na configuração de roteamento de voz Skype for Business
 
**Resumo:** Saiba como revisar, publicar ou cancelar alterações de configuração de roteamento de voz Skype for Business Server usando o painel de controle Skype for Business Server voz.
  
Depois de fazer alterações em qualquer uma das  configurações em páginas no grupo Roteamento de Voz, execute este procedimento para revisar, publicar ou cancelar as alterações pendentes.
  
> [!IMPORTANT]
> Certifique-se de que apenas um usuário por vez modifica as configurações de Roteamento de Voz. 
  
> [!NOTE]
> Todas as alterações pendentes devem ser publicadas ao mesmo tempo executando o **comando Commit all.** Não é possível publicar seletivamente as alterações pendentes. Antes de publicar alterações pendentes, execute o comando **Revisar** alterações nãocommitidas e cancele as alterações de configuração que você não deseja publicar.
  
> [!NOTE]
> Se você navegar para longe das páginas no grupo **Roteamento** de Voz antes de cometer alterações pendentes, todas as alterações pendentes serão perdidas. No entanto, você pode exportar a configuração atual (incluindo quaisquer alterações pendentes) para um arquivo de configuração de voz e, em seguida, importar e publicar a configuração atualizada. Para obter detalhes, [consulte Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Para revisar, publicar ou cancelar alterações de configuração de roteamento de voz

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
4. Faça as alterações de configuração que você deseja para as configurações em cada página do grupo **roteamento de** voz.
    
5. Para revisar as alterações pendentes sem publicá-las, selecione **Revisar** alterações não comprometidas no menu **Confirmação.**
    
6. Se você quiser cancelar qualquer uma das alterações pendentes, faça um dos seguintes:
    
   - Selecione **Cancelar todas as alterações não comprometidas** no menu **Confirmação.**
    
   - Navegue até a  guia da página Roteamento de Voz que tem alterações pendentes que você deseja cancelar, selecione o item com as alterações pendentes, clique em Confirmação **e** clique em Cancelar alterações **selecionadas.**
    
7. Depois de revisar todas as alterações pendentes e cancelar qualquer uma que não queira publicar, clique em Confirmação **e** clique em **Comprometer tudo.**
    
8. Na caixa **de diálogo Configuração** de Voz Não Configurações, que exibe uma lista de todas as alterações pendentes, clique em **OK**. 
    
    Quando Skype for Business Server Painel de Controle tiver comprometido as alterações, a mensagem **de** configuração de roteamento de voz publicada com êxito será exibida.
    

