---
title: Verificar a conclusão da replicação de usuário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Ao executar o cmdlet Move-CsUser, você pode ter uma falha porque as informações do usuário entre os serviços de domínio Active Directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estão fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o Skype for Business Server 2019 pool. O processo de sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 ocorre quando o servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez. Depois disso, a sincronização é baseada no intervalo de Duplicador do usuário. Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet Move-CsUser.
ms.openlocfilehash: 12bb3c29f703287934358f331dc945830e318afb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243708"
---
# <a name="verify-user-replication-has-completed"></a>Verificar a conclusão da replicação de usuário

Ao executar o cmdlet **move-CsUser** , você pode ter uma falha se as informações do usuário entre os serviços de domínio Active Directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estiverem fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o Skype for Business Server 2019 pool. O processo de sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 ocorre quando o servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez. Depois disso, a sincronização é baseada no intervalo do Duplicador do usuário. Conclua as etapas a seguir para verificar se a duplicação do usuário foi concluída antes de executar o cmdlet **move-CsUser** . 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Para verificar se a duplicação do usuário foi concluída

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Clique no menu **Iniciar** e, em seguida, clique em **executar**. 
    
3. Insira **eventvwr. exe**e clique em **OK**.
    
4. Em Visualizador de eventos, clique em **logs de aplicativos e serviços** para expandi-lo e, em seguida, selecione Skype for Business Server. 
    
5. No painel **ações** , clique em **Filtrar log atual**.
    
6. Na lista **fontes de eventos** , clique em duplicador de **usuários ls**.
    
7. Em ** \<todas as\>identificações de evento**, insira **30024**e clique em **OK**. 
    
8. Na lista eventos filtrados, na guia **geral** , procure por uma entrada que declara que a duplicação do usuário foi concluída com êxito. 
    

