---
title: Exportar ou importar um arquivo de configuração de rota de voz no Skype for Business
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumo: Saiba como exportar ou importar um arquivo de configuração de roteamento de voz no Skype for Business Server usando o Painel de Controle do Skype for Business Server.'
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830351"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exportar ou importar um arquivo de configuração de rota de voz no Skype for Business
 
**Resumo:** Saiba como exportar ou importar um arquivo de configuração de roteamento de voz no Skype for Business Server usando o Painel de Controle do Skype for Business Server.
  
Se você deseja salvar sua configuração de roteamento de voz sem publicá-la, siga estas etapas para salvar e recuperar um instantâneo da configuração de roteamento de voz. 
  
Quando você importa um arquivo de configuração de roteamento de voz (.vcfg), mas houve  alterações na configuração de roteamento de voz no servidor enquanto isso, as páginas no grupo roteamento de voz no Painel de Controle do Skype for Business Server indicarão que há alterações não confirmados no roteamento de voz. Essas alterações não confirmadas são as diferenças entre as duas configurações que exigem reconciliação.
  
Se você tiver feito alterações não confirmados nas configurações de qualquer página do grupo, as alterações serão salvas no arquivo de configuração de voz exportado (.vcfg). Isso permite que você faça alterações de configuração de roteamento de voz durante várias sessões antes de publicar as alterações. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Para exportar uma configuração de roteamento de voz

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Roteamento de voz**.
    
4. No menu **Ações**, clique em **Exportar configuração**.
    
5. Especifique um local e nome de arquivo e então clique em **Salvar**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Para importar uma configuração de roteamento de voz

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
4. No menu **Ações**, clique em **Importar Configuração**.
    
5. Localize o arquivo de configuração que você deseja importar e clique em **Abrir**.
    
6. Clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.
    
    > [!NOTE]
    > Sempre que importar um arquivo de configuração de voz, você deve executar o comando **Confirmar tudo** para publicar a alteração na configuração. Para obter detalhes, [consulte Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.
  

