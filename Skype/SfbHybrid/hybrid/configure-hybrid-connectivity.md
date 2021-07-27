---
title: Configurar a conectividade híbrida | Implantar Skype for Business Server conexão 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instruções para implementar a conectividade híbrida entre Skype for Business Server e Teams.
ms.openlocfilehash: 832aa989d8f698ac939dbf522476fb9dd6bfb2b8
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574056"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Configurar conectividade híbrida entre Skype for Business Server e Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Resumo:** Leia este tópico para saber como configurar a conectividade híbrida entre Skype for Business Server e Teams.  A conectividade híbrida permite que você mova seus usuários locais para Teams e permite que os usuários aproveitem os serviços de nuvem.
  
Antes de executar as etapas deste tópico, você deve ter lido [Plan hybrid connectivity between Skype for Business Server and Teams](plan-hybrid-connectivity.md).
  
A tabela a seguir lista as tarefas necessárias para configurar Skype for Business conectividade híbrida e fornece links para os artigos associados para obter mais informações.
  
|Etapa|Descrição|
|:-----|:-----|
|Criar uma conta de locatário para Microsoft 365   <br/> |Saiba mais Microsoft 365 em [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para garantir que seu ambiente esteja pronto para Microsoft 365, consulte Os [Requisitos do Sistema](https://products.office.com/office-system-requirements).  <br/> Para obter detalhes sobre como configurar Microsoft 365, consulte [Getting Started with Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Adicione seu domínio à sua organização Microsoft 365 e verifique a propriedade  <br/> | Você deve adicionar seu domínio à sua Microsoft 365 e, em seguida, seguir as etapas para validar o domínio com Microsoft 365. Isso é para confirmar se você é o proprietário do domínio. <br/> Para adicionar seu domínio à sua Microsoft 365, siga as etapas descritas em [Adicionar um domínio a](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)Microsoft 365 .  <br/> |
|Configurar a sincronização do Active Directory  <br/> |A sincronização do Active Directory mantém o Active Directory local continuamente sincronizado com Microsoft 365. Isso permite criar versões sincronizadas de cada conta de usuário e grupo.  <br/> <br> **Importante:** Você precisa sincronizar as contas do AD para todos os usuários Skype for Business em sua organização entre suas implantações locais e online, mesmo que os usuários não sejam movidos para Teams. Se você não sincronizar todos os usuários, a comunicação entre usuários locais e online em sua organização pode não funcionar conforme o esperado. Para obter mais informações, [consulte Configure Azure AD Conexão para ambientes híbridos](configure-azure-ad-connect.md).         |
| Configure o Skype for Business híbrido | Há três etapas básicas: <br><br> 1. Configure seu ambiente local para federar com Microsoft 365. <br> 2. Configure seu ambiente local para confiar Microsoft 365 e habilitar o espaço de endereço SIP compartilhado com Microsoft 365.<br> 3. Habilita o espaço de endereço SIP compartilhado em sua Microsoft 365 organização. <br><br> Além disso, se você tiver Exchange local, talvez você queira configurar o OAuth entre seus ambientes Exchange locais e online. <br> <br>Para obter mais informações, consulte [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).
|Mover usuários piloto  <br/> |Depois de concluir as etapas para preparar e configurar seu ambiente para Teams, você pode começar a mover usuários piloto para sua organização Microsoft 365 online. Para obter mais informações, consulte [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md).  <br/> |
