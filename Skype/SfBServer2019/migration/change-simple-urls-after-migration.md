---
title: Alterar URLs simples após a migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: O Skype for Business Server oferece suporte a URLs simples.
ms.openlocfilehash: 786e3f5d7ed273c0f3c2ccc39ef1b539714de61b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298323"
---
# <a name="change-simple-urls-after-migration"></a>Alterar URLs simples após a migração

O Skype for Business Server oferece suporte a três URLs simples:
  
- A **reunião** é usada como a URL base para todas as conferências no site ou na organização. Com a URL simples de reunião, os links para ingressar em reuniões são fáceis de compreender e fáceis de se comunicar e distribuir. 
    
- **** A discagem permite o acesso à página da Web configurações de conferência discada. A URL simples Dial-in é incluída em todos os convites de reunião para que os usuários que desejam discar para a reunião possam acessar o número de telefone e as informações de PIN necessárias. 
    
- O **administrador** permite acesso rápido ao painel de controle do Skype for Business Server. A URL simples de Admin é parte interna da sua organização. 
    
Depois de migrar para o Skype for Business Server, você deve estar ciente de como a alteração afeta seus registros DNS e certificados para URLs simples. Se o diretor herdado do Skype for Business permanecer em uso na topologia, não será necessária nenhuma alteração nas URLs simples. Se o diretor do servidor do Skype for Business for removido da topologia após a migração, os registros DNS de URL simples deverão ser atualizados para apontar para um dos pools do servidor do Skype for Business. No entanto, sempre que você alterar um nome de URL simples, você deve executar Enable-CsComputer em cada director e servidor front-end para registrar a alteração.

## <a name="to-update-the-meet-simple-url"></a>Para atualizar a URL de reunião simples

1. No construtor de topologias, clique com o botão direito do mouse no nó superior do **Skype for Business Server**e clique em **Editar propriedades**.
    
2. Selecione **URLs simples** no painel esquerdo e, abaixo de **URLs de reunião:** selecione a URL do encontro e clique em **Editar URL**.
    
3. Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada. 
    
## <a name="to-update-the-admin-simple-url"></a>Para atualizar a URL simples de administrador

1. No construtor de topologias, clique com o botão direito do mouse no nó superior do **Skype for Business Server**e clique em **Editar propriedades**.
    
2. Selecione **URLs simples** no painel esquerdo e, em seguida, abaixo da caixa **URL de acesso administrativo** , insira a URL simples que você deseja para acesso administrativo ao painel de controle do Skype for Business Server e clique em **OK**.
    
   > [!TIP]
   > Nós recomendamos que você use a URL do administrador mais simples possível. A opção mais simples é https://admin. <em> \<domínio\></em>. 
  
## <a name="see-also"></a>Confira também

[Requisitos de DNS para URLs simples no Skype for Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
