---
title: Verificar a replicação de usuário foi concluída
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Ao executar o cmdlet Move-CsUser, você pode enfrentar uma falha porque as informações de usuário entre os serviços de domínio Active Directory (AD DS) e o Skype para bancos de dados corporativos Server 2019 estão fora de sincronia porque a replicação inicial está incompleta. O tempo que leva para a conclusão bem-sucedida do Skype para a sincronização inicial do serviço do replicador de usuário do Business Server 2019 depende do número de controladores de domínio que estão hospedados na floresta do Active Directory que hospeda o Skype para negócios Pool de servidor 2019. O Skype para o processo de sincronização inicial do replicador de usuário do Business Server 2019 serviço ocorre quando o Skype para Business Server 2019 servidor Front-End é iniciado pela primeira vez. Depois disso, a sincronização, em seguida, com base no intervalo de replicador de usuários. Conclua as seguintes etapas para verificar se a replicação de usuário foi concluída antes de executar o cmdlet Move-CsUser.
ms.openlocfilehash: 43b2822303676d209dc14a3b2e06368a7d24e174
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027841"
---
# <a name="verify-user-replication-has-completed"></a>Verificar a replicação de usuário foi concluída

Ao executar o cmdlet **Move-CsUser** , você pode enfrentar uma falha se as informações do usuário entre os serviços de domínio Active Directory (AD DS) e o Skype para bancos de dados corporativos Server 2019 estão fora de sincronia porque a replicação inicial está incompleta. O tempo que leva para a conclusão bem-sucedida do Skype para a sincronização inicial do serviço do replicador de usuário do Business Server 2019 depende do número de controladores de domínio que estão hospedados na floresta do Active Directory que hospeda o Skype para negócios Pool de servidor 2019. O Skype para o processo de sincronização inicial do replicador de usuário do Business Server 2019 serviço ocorre quando o Skype para Business Server 2019 servidor Front-End é iniciado pela primeira vez. Depois disso, a sincronização baseia-se no intervalo de replicador de usuários. Conclua as seguintes etapas para verificar se a replicação de usuário que foi concluída antes de executar o cmdlet **Move-CsUser** . 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Para verificar se a replicação usuário foi concluída

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Clique no menu **Iniciar** e, em seguida, clique em **Executar**. 
    
3. Insira **eventvwr.exe**e clique em **Okey**.
    
4. No Visualizador de eventos, clique em **logs de aplicativos e serviços** para expandi-lo e selecione Skype para Business Server. 
    
5. No painel **ações** , clique em **Filtrar Log atual**.
    
6. Na lista **fontes de evento** , clique em **LS User Replicator**.
    
7. Em ** \<todas as IDs de evento\>**, insira **30024**e clique em **Okey**. 
    
8. Na lista de eventos filtrados, na guia **Geral** , procure uma entrada que afirma que a replicação usuário foi concluída com êxito. 
    

