---
title: Alterar URLs simples após a migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server oferece suporte a URLs simples.
ms.openlocfilehash: 02f4cc729a50459a8125e216265b935d557007c6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892706"
---
# <a name="change-simple-urls-after-migration"></a>Alterar URLs simples após a migração

Skype para Business Server suporta três URLs simples:
  
- **Reunir** é usado como a URL base para todas as conferências no local ou organização. Com o URL reunir simples, links para ingressar em reuniões são fáceis de compreender e fáceis de se comunicar e distribuir. 
    
- **Discada** permite o acesso a página da Web configurações de conferência discada. A URL simples Dial-in é incluída em todos os convites de reunião para que os usuários que desejam discar para a reunião possam acessar o número de telefone e as informações de PIN necessárias. 
    
- **Admin** permite acesso rápido ao Skype para painel de controle do servidor de negócios. A URL simples de Admin é parte interna da sua organização. 
    
Após migrar para o Skype para Business Server, você deve estar ciente como a alteração afeta seus registros DNS e certificados para URLs simples. Se o Skype herdado para o Diretor de servidor de negócios permanecer em uso na topologia, nenhuma alteração aos seus URLs simples é necessárias. Se o Skype para negócios servidor Diretor for removido da topologia após a migração, os registros de DNS de URL simples devem ser atualizados para apontar para um do Skype para pools de servidor de negócios. Sempre que você alterar um nome de URL simple, no entanto, você deve executar Enable-CsComputer em cada diretor e o servidor Front-End para registrar a alteração.

## <a name="to-update-the-meet-simple-url"></a>Para atualizar o URL reunir simples

1. No construtor de topologia, clique com botão direito no nó superior **Skype para Business Server**e, em seguida, clique em **Editar propriedades**.
    
2. Selecione **URLs simples** no painel esquerdo, em seguida, abaixo **URLs de reunião:** selecione a URL de reunião e clique em **Editar URL**.
    
3. Atualize a URL para o valor desejado e, em seguida, clique em **Okey** para salvar a URL editada. 
    
## <a name="to-update-the-admin-simple-url"></a>Para atualizar a URL simple de Admin

1. No construtor de topologia, clique com botão direito no nó superior **Skype para Business Server**e, em seguida, clique em **Editar propriedades**.
    
2. Selecione **URLs simples** no painel esquerdo, em seguida, abaixo caixa **URL de acesso administrativo** , digite a URL simples que você deseja para acesso administrativo ao Skype para painel de controle do Business Server e clique em **Okey**.
    
   > [!TIP]
   > Nós recomendamos que você use a URL do administrador mais simples possível. É a opção mais simples https://admin. <em> \<domínio\></em>. 
  
## <a name="see-also"></a>Consulte Também

[Requisitos de DNS para URLs simples no Skype para Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
