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
description: Ao executar o cmdlet Move-CsUser, você pode ter uma falha porque as informações do usuário entre os Serviços de Domínio do Active Directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estão fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço replicador de usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool Skype for Business Server 2019. O Skype for Business Server de sincronização inicial do serviço replicador de usuário 2019 ocorre quando o servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez. Depois disso, a sincronização se baseia no intervalo do Replicador de Usuário. Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet Move-CsUser.
ms.openlocfilehash: 0fe1c205b04ed32f5ac4281e555d5a44262905aa23b74eb69148d447337b59f7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325678"
---
# <a name="verify-user-replication-has-completed"></a>Verificar a conclusão da replicação de usuário

Ao executar o cmdlet **Move-CsUser,** você poderá ter uma falha se as informações do usuário entre os Serviços de Domínio do Active Directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estão fora de sincronização porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço replicador de usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool Skype for Business Server 2019. O Skype for Business Server de sincronização inicial do serviço replicador de usuário 2019 ocorre quando o servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez. Depois disso, a sincronização é baseada no intervalo replicador de usuários. Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet **Move-CsUser.** 
  
### <a name="to-verify-that-user-replication-has-completed"></a>Para verificar que a replicação de usuário foi concluída

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Clique no menu **Iniciar** e em **Executar**. 
    
3. Digite **eventvwr.exe** e clique em **OK**.
    
4. No Visualizador de Eventos, clique em **Logs de Aplicativos** e Serviços para expandi-lo e selecione Skype for Business Server. 
    
5. No painel **Ações**, clique em **Filtrar Log Atual**.
    
6. Na lista **Fontes de evento**, clique em **Replicador de Usuário LS**.
    
7. In **\<All Event IDs\>** , enter **30024**, and then click **OK**. 
    
8. Na lista de eventos filtrados, na guia **Geral,** procure uma entrada informando que a replicação do usuário foi concluída com êxito. 
    

