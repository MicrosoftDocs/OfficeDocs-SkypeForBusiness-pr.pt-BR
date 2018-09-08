---
title: Exportar ou importar um arquivo de configuração de rota de voz no Skype para negócios
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumo: Saiba como exportar ou importar um arquivo de configuração de roteamento de voz no Skype para Business Server usando o Skype para painel de controle do servidor de negócios.'
ms.openlocfilehash: 5cf9021a1cc18daf90fc719723962959142ad92e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886786"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Exportar ou importar um arquivo de configuração de rota de voz no Skype para negócios
 
**Resumo:** Saiba como exportar ou importar um arquivo de configuração de roteamento de voz no Skype para Business Server usando o Skype para painel de controle do servidor de negócios.
  
Se quiser salvar sua configuração de roteamento de voz sem publicá-la, siga estas etapas para salvar e recuperar um instantâneo da sua configuração de roteamento de voz. 
  
Quando você importa um arquivo de configuração roteamento voz (.vcfg), mas tiver sofrido alterações à configuração de voz roteamento no servidor enquanto isso, as páginas do grupo de **Roteamento de voz** no Skype para painel de controle do Business Server indicará que existe foram feitas alterações não confirmadas roteamento de voz. Essas alterações não confirmadas são as diferenças entre as duas configurações que exigem reconciliação.
  
Se você tiver feito as alterações não confirmadas às configurações em qualquer página dentro do grupo, as alterações são salvas no arquivo de configuração de voz exportado (.vcfg). Isso permite que você faça alterações na configuração de roteamento durante várias sessões antes de publicar as alterações de voz. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Para exportar uma configuração de roteamento de voz

1. Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.
    
2. Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
4. No menu **Ações**, clique em **Exportar configuração**.
    
5. Especifique um local e nome de arquivo e então clique em **Salvar**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Para importar uma configuração de roteamento de voz

1. Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.
    
2. Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
4. No menu **Ações**, clique em **Importar Configuração**.
    
5. Localize o arquivo de configuração que você deseja importar e clique em **Abrir**.
    
6. Clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.
    
    > [!NOTE]
    > Sempre que importar um arquivo de configuração de voz, você deve executar o comando **Confirmar tudo** para publicar a alteração na configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.
  

