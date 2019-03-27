---
title: Publicar alterações pendentes para a configuração de roteamento de voz no Skype para negócios
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Resumo: Saiba como revisar, publicar ou Cancelar alterações na configuração roteamento voz no Skype para Business Server usando o Skype para painel de controle do servidor de negócios.'
ms.openlocfilehash: 9878e719234a5d7eff2e7321fa71e30c094d489a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897703"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Publicar alterações pendentes para a configuração de roteamento de voz no Skype para negócios
 
**Resumo:** Aprenda a revisar, publicar ou Cancelar alterações na configuração roteamento voz no Skype para Business Server usando o Skype para painel de controle do servidor de negócios.
  
Após fazer alterações em qualquer uma das definições de configuração nas páginas do grupo **Roteamento de Voz**, execute este procedimento para examinar, publicar ou cancelar as alterações pendentes.
  
> [!IMPORTANT]
> Certifique-se de que somente um usuário por vez modifique as definições de configurações do Roteamento de voz. 
  
> [!NOTE]
> Todas as alterações pendentes devem ser publicadas ao mesmo tempo, executando o comando **Confirmar todos**. Não é possível publicar seletivamente as alterações pendentes. Antes de publicar as alterações pendentes, execute o comando **Revisar alterações não confirmadas** e cancele qualquer alteração de configuração que não deseja publicar.
  
> [!NOTE]
> Se você navegar longe das páginas do grupo **Roteamento de voz** antes de confirmar as alterações pendentes, todas as alterações pendentes serão perdida. No entanto, é possível exportar a configuração atual (incluindo quaisquer alterações pendentes) para um arquivo de configuração de voz e, em seguida, importar e publicar a configuração atualizada. Para obter detalhes, consulte [Exportar ou importar arquivo Skype para negócios de uma configuração de rota de voz](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Para revisar, publicar ou cancelar as alterações de configuração do roteamento de voz

1. Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.
    
2. Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
4. Faça as alterações de configuração que deseja para as configurações em cada página do grupo **Roteamento de voz**.
    
5. Para revisar as alterações pendentes sem publicá-las, selecione **Revisar alterações não confirmadas** no menu **Confirmar**.
    
6. Se você deseja cancelar qualquer alteração pendente, siga um destes procedimentos:
    
   - Selecione **Cancelar todas as alterações não confirmadas** no menu **Confirmar**.
    
   - Navegue até a guia da página **Roteamento de voz** que possui as alterações pendente que deseja cancelar, selecione o item com as alterações pendentes, clique em **Confirmar** e em **Cancelar alterações selecionadas**.
    
7. Após revisar todas as alterações pendentes e cancelar qualquer uma que não deseja publicar, clique em **Confirmar** e em **Confirmar todas**.
    
8. Na caixa de diálogo **Definições da configuração de voz não confirmadas** que exibe uma lista de todas as alterações pendentes, clique em **OK**. 
    
    Quando Skype para painel de controle do Business Server confirmar as alterações, é exibida a mensagem **publicada com êxito a configuração de roteamento de voz** .
    

