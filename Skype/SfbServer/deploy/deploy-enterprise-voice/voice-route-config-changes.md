---
title: Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Resumo: Saiba como revisar, publicar ou cancelar alterações de configuração de roteamento de voz no Skype for Business Server usando o Painel de Controle do Skype for Business Server.'
ms.openlocfilehash: 6b75b6a1135cf9abde9551112fc9c29579862a8b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830391"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business
 
**Resumo:** Saiba como revisar, publicar ou cancelar alterações de configuração de roteamento de voz no Skype for Business Server usando o Painel de Controle do Skype for Business Server.
  
Depois de fazer alterações em qualquer uma das  definições de configuração nas páginas do grupo Roteamento de Voz, execute este procedimento para revisar, publicar ou cancelar as alterações pendentes.
  
> [!IMPORTANT]
> Certifique-se de que apenas um usuário por vez modifica as definições de configuração do Roteamento de Voz. 
  
> [!NOTE]
> Todas as alterações pendentes devem ser publicadas ao mesmo tempo executando o **comando Commit all.** Não é possível publicar seletivamente as alterações pendentes. Antes de publicar as alterações  pendentes, execute o comando Revisar alterações não confirmados e cancele quaisquer alterações de configuração que você não queira publicar.
  
> [!NOTE]
> Se você sair das páginas  do grupo Roteamento de Voz antes de comprometer as alterações pendentes, todas as alterações pendentes serão perdidas. No entanto, você pode exportar a configuração atual (incluindo quaisquer alterações pendentes) para um arquivo de configuração de voz e, em seguida, importar e publicar a configuração atualizada. Para obter detalhes, [consulte Exportar ou importar um arquivo de configuração de](voice-route-configuration-import-export.md)rota de voz no Skype for Business. 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Para revisar, publicar ou cancelar alterações de configuração de roteamento de voz

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
4. Faça as alterações de configuração que você deseja para as configurações em cada página do grupo **roteamento de** voz.
    
5. Para revisar as alterações pendentes sem publicá-las, selecione Revisar alterações **não** confirmados **no** menu Confirmação.
    
6. Se você quiser cancelar qualquer uma das alterações pendentes, faça um dos seguintes:
    
   - Selecione **Cancelar todas as alterações não confirmados** **no** menu Confirmação.
    
   - Navegue até a  guia da página Roteamento de Voz que tem alterações pendentes que você deseja cancelar, selecione o item com as alterações pendentes, clique em Confirmação e clique em Cancelar alterações **selecionadas.**
    
7. Depois de revisar todas as alterações pendentes e cancelar qualquer uma que não deseja publicar, clique em Confirmação e em **Confirmação de todos.**
    
8. Na caixa de diálogo Definições de Configuração de Voz Não Confirmados, que exibe uma lista de todas as alterações **pendentes,** clique em **OK.** 
    
    Quando o Painel de Controle do Skype for Business Server tiver comprometido as alterações, a mensagem de configuração de roteamento de voz publicada **com** êxito será exibida.
    

