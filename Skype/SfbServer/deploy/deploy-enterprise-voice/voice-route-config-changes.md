---
title: Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Resumo: saiba como revisar, publicar ou cancelar alterações de configuração de roteamento de voz no Skype for Business Server usando o painel de controle do Skype for Business Server.'
ms.openlocfilehash: 6a13c2a2b2b1221203fbed84948b803a6c2ea1db
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239919"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business
 
**Resumo:** Saiba como revisar, publicar ou cancelar alterações de configuração de roteamento de voz no Skype for Business Server usando o painel de controle do Skype for Business Server.
  
Após fazer alterações em qualquer uma das definições de configuração nas páginas do grupo **Roteamento de Voz**, execute este procedimento para examinar, publicar ou cancelar as alterações pendentes.
  
> [!IMPORTANT]
> Certifique-se de que somente um usuário por vez modifique as definições de configurações do Roteamento de voz. 
  
> [!NOTE]
> Todas as alterações pendentes devem ser publicadas ao mesmo tempo, executando o comando **Confirmar todos**. Não é possível publicar seletivamente as alterações pendentes. Antes de publicar as alterações pendentes, execute o comando **Revisar alterações não confirmadas** e cancele qualquer alteração de configuração que não deseja publicar.
  
> [!NOTE]
> Se você navegar longe das páginas do grupo **Roteamento de voz** antes de confirmar as alterações pendentes, todas as alterações pendentes serão perdida. No entanto, é possível exportar a configuração atual (incluindo quaisquer alterações pendentes) para um arquivo de configuração de voz e, em seguida, importar e publicar a configuração atualizada. Para obter detalhes, consulte [exportar ou importar um arquivo de configuração de rota de voz no Skype for Business](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Para revisar, publicar ou cancelar as alterações de configuração do roteamento de voz

1. Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.
    
2. Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
4. Faça as alterações de configuração que deseja para as configurações em cada página do grupo **Roteamento de voz**.
    
5. Para revisar as alterações pendentes sem publicá-las, selecione **Revisar alterações não confirmadas** no menu **Confirmar**.
    
6. Se você deseja cancelar qualquer alteração pendente, siga um destes procedimentos:
    
   - Selecione **Cancelar todas as alterações não confirmadas** no menu **Confirmar**.
    
   - Navegue até a guia da página **Roteamento de voz** que possui as alterações pendente que deseja cancelar, selecione o item com as alterações pendentes, clique em **Confirmar** e em **Cancelar alterações selecionadas**.
    
7. Após revisar todas as alterações pendentes e cancelar qualquer uma que não deseja publicar, clique em **Confirmar** e em **Confirmar todas**.
    
8. Na caixa de diálogo **Definições da configuração de voz não confirmadas** que exibe uma lista de todas as alterações pendentes, clique em **OK**. 
    
    Quando o painel de controle do Skype for Business Server tiver confirmado as alterações, será exibida a mensagem de **configuração de roteamento de voz publicada com êxito** .
    

