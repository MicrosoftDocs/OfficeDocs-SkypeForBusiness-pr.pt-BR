---
title: Configurar conectividade híbrida | Implantar o Skype for Business Server 2019 Connect
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
description: Instruções para implementar a conectividade híbrida entre o Skype for Business Server e o Skype for Business online.
ms.openlocfilehash: 54029297cb17da79d706f62ecdf9109747f9ce20
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008613"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurar a conectividade híbrida entre o Skype for Business Server e o Office 365

**Resumo:** Leia este tópico para saber como configurar a conectividade híbrida entre o Skype for Business Server e o Teams ou o Skype for Business online.  A conectividade híbrida permite que você mova seus usuários locais para o Microsoft Teams ou o Skype for Business Online e permite que os usuários aproveitem os serviços em nuvem.
  
Antes de executar as etapas deste tópico, você deve ter uma [conectividade híbrida do plano de leitura entre o Skype for Business Server e o Office 365](plan-hybrid-connectivity.md).
  
A tabela a seguir lista as tarefas necessárias para configurar a conectividade híbrida do Skype for Business e fornece links para os artigos associados para obter mais informações.
  
|Etapa|Descrição|
|:-----|:-----|
|Criar uma conta de locatário para o Office 365   <br/> |Saiba mais sobre o Office 365 no [office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para certificar-se de que seu ambiente está pronto para o Office 365, confira os [requisitos do sistema](https://products.office.com/office-system-requirements).  <br/> Para obter detalhes sobre como configurar o Office 365, consulte [Getting Started with Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Adicione seu domínio ao seu locatário do Office 365 e verifique a propriedade  <br/> | Você deve adicionar seu domínio ao seu locatário do Office 365 e, em seguida, siga as etapas para validar o domínio com o Office 365. Isso é para confirmar que você é o proprietário do domínio. <br/> Para adicionar seu domínio ao seu locatário do Office 365, siga as etapas descritas em [Adicionar um domínio ao Office 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurar a sincronização do Active Directory  <br/> |A sincronização do Active Directory mantém o seu Active Directory no local sincronizado continuamente com o Office 365. Isso permite que você crie versões sincronizadas de cada conta de usuário e grupo.  <br/> <br> **Importante:** Você precisa sincronizar as contas do AD para todos os usuários do Skype for Business em sua organização entre suas implantações locais e online, mesmo que os usuários não sejam movidos para o Microsoft Teams ou o Skype for Business online. Se você não sincronizar todos os usuários, a comunicação entre os usuários locais e online em sua organização poderá não funcionar conforme o esperado. Para obter mais informações, consulte [Configurar o Azure ad Connect para ambientes híbridos](configure-azure-ad-connect.md).         |
| Configurar o Skype for Business híbrido | Há três etapas básicas: <br><br> 1. configure seu ambiente local para federação com o Office 365. <br> 2. configure seu ambiente local para confiar no Office 365 e habilitar o espaço de endereçamento SIP compartilhado com o Office 365.<br> 3. habilitar o espaço de endereçamento SIP compartilhado no seu locatário do Office 365. <br><br> Além disso, se você tiver o Exchange local, convém configurar o OAuth entre seus ambientes do Exchange local e do Skype for Business online. <br> <br>Para obter mais informações, consulte [Configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md).
|Mover usuários piloto  <br/> |Após concluir as etapas para preparar e configurar seu ambiente para o Teams ou o Skype for Business Online, você pode começar a mover os usuários do piloto para o seu locatário online do Office 365. Para obter mais informações, consulte [move users from local to Skype for Business online](move-users-from-on-premises-to-skype-for-business-online.md) e [move users from local to Teams](move-users-from-on-premises-to-Teams.md).  <br/> |