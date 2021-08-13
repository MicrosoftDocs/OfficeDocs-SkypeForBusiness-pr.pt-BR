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
description: Skype for Business Server dá suporte a URLs simples.
ms.openlocfilehash: c3d78387ae0bcf16204e2fcaa4ff7db3549334fe814a014a88c80e8ab6658d5b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324720"
---
# <a name="change-simple-urls-after-migration"></a>Alterar URLs simples após a migração

Skype for Business Server suporta três URLs simples:
  
- **Reunir** é usado como URL base para todas as conferências no site ou na organização. Com o URL Reunir simples, os links para ingressar em reuniões são fáceis de compreender, de comunicar e distribuir. 
    
- **Discar** possibilita o acesso à página da web Configurações de Conferência Discada. O URL Discar é incluído em todos os convites de reuniões para que o usuário que desejar discar para ingressar na reunião possa obter acesso ao número de telefone necessário, bem como as informações do PIN. 
    
- **O** administrador habilita o acesso rápido ao painel Skype for Business Server controle. A URL simples de Admin é interna à organização. 
    
Depois de migrar para Skype for Business Server, você deve estar ciente de como a alteração afeta seus registros DNS e certificados para URLs simples. Se o diretor Skype for Business Server legado permanecer em uso na topologia, nenhuma alteração nas URLs simples será necessária. Se o Skype for Business Server diretor for removido da topologia após a migração, os registros DNS de URL simples devem ser atualizados para apontar para um dos pools de Skype for Business Server. Contudo, sempre que você alterar o nome de um URL simples, você deve executar o Enable-CsComputer em cada servidor Diretor e Front End para registrar a alteração.

## <a name="to-update-the-meet-simple-url"></a>Para atualizar a URL simples meet

1. No Construtor de Topologias, clique com o botão direito do mouse no nó **superior** Skype for Business Server e clique em **Editar Propriedades**.
    
2. Selecione **URLs simples** no painel esquerdo e abaixo **URLs** de Reunião: selecione a URL de Reunião e clique em **Editar URL**.
    
3. Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada. 
    
## <a name="to-update-the-admin-simple-url"></a>Para atualizar a URL simples do Administrador

1. No Construtor de Topologias, clique com o botão direito do mouse no nó **superior** Skype for Business Server e clique em **Editar Propriedades**.
    
2. Selecione **URLs** simples no painel esquerdo e, abaixo da caixa URL de acesso administrativo, insira a **URL** simples que você deseja para acesso administrativo Skype for Business Server Painel de Controle e clique em **OK**.
    
   > [!TIP]
   > Recomendamos usar a URL mais simples possível para a URL Admin. A opção mais simples é https://admin <em>\<domain\></em> . 
  
## <a name="see-also"></a>Confira também

[Requisitos dns para URLs simples em Skype for Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
