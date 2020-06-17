---
title: Alterar URLs simples após a migração
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: O Skype for Business Server oferece suporte a URLs simples.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753901"
---
# <a name="change-simple-urls-after-migration"></a>Alterar URLs simples após a migração

O Skype for Business Server oferece suporte a três URLs simples:
  
- **Reunir** é usado como URL base para todas as conferências no site ou na organização. Com o URL Reunir simples, os links para ingressar em reuniões são fáceis de compreender, de comunicar e distribuir. 
    
- **Discar** possibilita o acesso à página da web Configurações de Conferência Discada. O URL Discar é incluído em todos os convites de reuniões para que o usuário que desejar discar para ingressar na reunião possa obter acesso ao número de telefone necessário, bem como as informações do PIN. 
    
- O **administrador** permite acesso rápido ao painel de controle do Skype for Business Server. A URL simples de Admin é interna à organização. 
    
Após migrar para o Skype for Business Server, você deve estar ciente de como a alteração impacta seus registros DNS e certificados para URLs simples. Se o diretor de servidor do Skype for Business herdado permanecer em uso na topologia, não será necessário fazer alterações nas suas URLs simples. Se o diretor do Skype for Business Server for removido da topologia após a migração, os registros DNS de URL simples devem ser atualizados para apontar para um dos pools do Skype for Business Server. Contudo, sempre que você alterar o nome de um URL simples, você deve executar o Enable-CsComputer em cada servidor Diretor e Front End para registrar a alteração.

## <a name="to-update-the-meet-simple-url"></a>Para atualizar a URL simples de reunião

1. No construtor de topologias, clique com o botão direito do mouse no nó superior **Skype for Business Server**e clique em **Editar propriedades**.
    
2. Selecione **URLs simples** no painel esquerdo e, abaixo das **URLs da reunião:** selecione a URL de reunião e clique em **Editar URL**.
    
3. Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada. 
    
## <a name="to-update-the-admin-simple-url"></a>Para atualizar a URL simples de administrador

1. No construtor de topologias, clique com o botão direito do mouse no nó superior **Skype for Business Server**e clique em **Editar propriedades**.
    
2. Selecione **URLs simples** no painel esquerdo e, em seguida, abaixo da caixa **URL de acesso administrativo** , digite a URL simples que você deseja para acesso administrativo ao painel de controle do Skype for Business Server e clique em **OK**.
    
   > [!TIP]
   > Recomendamos usar a URL mais simples possível para a URL Admin. A opção mais simples é https://admin . <em>\<domain\></em> . 
  
## <a name="see-also"></a>Confira também

[Requisitos de DNS para URLs simples no Skype for Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
