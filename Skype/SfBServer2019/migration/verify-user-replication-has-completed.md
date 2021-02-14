---
title: Verificar a conclusão da replicação de usuário
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
description: Ao executar o cmdlet Move-CsUser, você pode experimentar uma falha porque as informações do usuário entre os Serviços de Domínio active directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estão fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Replicador de Usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Skype for Business Server 2019. O processo de sincronização inicial do serviço Replicador de Usuários do Skype for Business Server 2019 ocorre quando o Servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez. Depois disso, a sincronização se baseia no intervalo do Replicador de Usuário. Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet Move-CsUser.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751643"
---
# <a name="verify-user-replication-has-completed"></a>Verificar a conclusão da replicação de usuário

Ao executar o cmdlet **Move-CsUser,** você pode experimentar uma falha se as informações do usuário entre os serviços de domínio active directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estão fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Replicador de Usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Skype for Business Server 2019. O processo de sincronização inicial do serviço Replicador de Usuários do Skype for Business Server 2019 ocorre quando o Servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez. Depois disso, a sincronização se baseia no intervalo do Replicador de usuários. Conclua as etapas a seguir para verificar se a replicação de usuário foi concluída antes de executar o cmdlet **Move-CsUser.** 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Para verificar que a replicação de usuário foi concluída

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Clique no menu **Iniciar** e em **Executar**. 
    
3. Digite **eventvwr.exe** e clique em **OK**.
    
4. No Visualizador de Eventos, clique em **Logs de** Aplicativos e Serviços para expandi-lo e selecione Skype for Business Server. 
    
5. No painel **Ações**, clique em **Filtrar Log Atual**.
    
6. Na lista **Fontes de evento**, clique em **Replicador de Usuário LS**.
    
7. Em **\<All Event IDs\>** , insira **30024** e clique em **OK**. 
    
8. Na lista de eventos filtrados, na guia Geral, procure uma entrada informando que a replicação de usuário foi concluída com êxito.  
    

