---
title: Configurar a conectividade híbrida | Implantar o Skype for Business Server 2019 connect
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
description: Instruções para implementar a conectividade híbrida entre o Skype for Business Server e o Skype for Business Online.
ms.openlocfilehash: 3a68d39062387952b7a43bb22599265a69bf7a61
ms.sourcegitcommit: 80b66127b3415c99f9468625add6a8f2c36bca74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48376744"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurar a conectividade híbrida entre o Skype for Business Server e o Office 365

**Resumo:** Leia este tópico para saber como configurar a conectividade híbrida entre o Skype for Business Server e o Teams ou o Skype for Business Online.  A conectividade híbrida permite que você mova seus usuários locais para o Teams ou o Skype for Business Online e permite que seus usuários aproveitem os serviços de nuvem.
  
Antes de executar as etapas neste tópico, você deve ter lido Plano de conectividade híbrida entre o [Skype for Business Server e o Office 365.](plan-hybrid-connectivity.md)
  
A tabela a seguir lista as tarefas necessárias para configurar a conectividade híbrida do Skype for Business e fornece links para os artigos associados para obter mais informações.
  
|Etapa|Descrição|
|:-----|:-----|
|Criar uma conta de locatário para o Office 365   <br/> |Saiba mais sobre o Office 365 no [Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> Para garantir que seu ambiente esteja pronto para o Office 365, consulte os [Requisitos do Sistema.](https://products.office.com/office-system-requirements)  <br/> Para obter detalhes sobre como configurar o Office 365, consulte [Getting Started with Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Adicionar seu domínio à sua organização do Office 365 e verificar a propriedade  <br/> | Você deve adicionar seu domínio à sua organização do Office 365 e seguir as etapas para validar o domínio com o Office 365. Isso é para confirmar que você é o proprietário do domínio. <br/> Para adicionar seu domínio à sua organização do Office 365, siga as etapas descritas em Adicionar um [domínio ao Office 365.](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)  <br/> |
|Configurar a sincronização do Active Directory  <br/> |A sincronização do Active Directory mantém seu Active Directory local continuamente sincronizado com o Office 365. Isso permite que você crie versões sincronizadas de cada conta de usuário e grupo.  <br/> <br> **Importante:** Você precisa sincronizar as contas do AD para todos os usuários do Skype for Business em sua organização entre suas implantações locais e online, mesmo que os usuários não sejam movidos para o Teams ou Skype for Business Online. Se você não sincronizar todos os usuários, a comunicação entre usuários locais e online em sua organização pode não funcionar conforme o esperado. Para obter mais informações, [consulte Configurar o Azure AD Connect para ambientes híbridos.](configure-azure-ad-connect.md)         |
| Configure o Skype for Business híbrido | Há três etapas básicas: <br><br> 1. Configure seu ambiente local para federar com o Office 365. <br> 2. Configure seu ambiente local para confiar no Office 365 e habilitar o espaço de endereço SIP compartilhado com o Office 365.<br> 3. Habilita o espaço de endereço SIP compartilhado em sua organização do Office 365. <br><br> Além disso, se você tem o Exchange no local, convém configurar o OAuth entre os ambientes do Exchange no local e do Skype for Business Online. <br> <br>Para obter mais informações, consulte [Configurar o Skype for Business híbrido.](configure-federation-with-skype-for-business-online.md)
|Mover usuários piloto  <br/> |Depois de concluir as etapas para preparar e configurar seu ambiente para o Teams ou o Skype for Business Online, você poderá começar a mover usuários piloto para sua organização online do Office 365. Para saber mais, confira Mover usuários do local para o [Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md) e mover usuários do local para o [Teams.](move-users-from-on-premises-to-Teams.md)  <br/> |
