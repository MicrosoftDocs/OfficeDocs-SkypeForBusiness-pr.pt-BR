---
title: Configurar a conectividade híbrida | Implantar Skype para Business Server 2019 de conexão
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para implementar a conectividade híbrida entre Skype para Business Server e do Skype para negócios Online.
ms.openlocfilehash: f15744e5cd7608c7cc6b1169844314d0a59c62f0
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29348895"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Configurar a conectividade híbrida entre Skype para Business Server e Office 365

**Resumo:** Leia este tópico para saber como configurar a conectividade híbrida entre Skype para servidor de negócios e equipes ou Skype para negócios Online.  Conectividade híbrida permite que você mova os usuários no local para equipes ou Skype para Business Online e permite que os usuários tirar proveito dos serviços de nuvem.
  
Antes de executar as etapas neste tópico, você deve ter lido [Planejar a conectividade híbrida entre Skype para Business Server e Office 365](plan-hybrid-connectivity.md).
  
A tabela a seguir lista as tarefas necessárias para configurar o Skype para conectividade híbrida de negócios e fornece links para os artigos associados para obter mais informações.
  
|Etapa|Descrição|
|:-----|:-----|
|Crie uma conta de locatário para o Office 365   <br/> |Saiba mais sobre o Office 365 no [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Para se certificar de que seu ambiente está pronto para o Office 365, consulte os [Requisitos do Sistema](https://products.office.com/en-US/office-system-requirements).  <br/> Para obter detalhes sobre como configurar o Office 365, consulte [Introdução ao Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Adicionar seu domínio ao seu locatário do Office 365 e verifique a propriedade  <br/> | Você precisa adicionar seu domínio ao seu locatário do Office 365 e, então, seguir as etapas para validar o domínio com o Office 365. Isso serve para confirmar que você é o proprietário do domínio. <br/> Para adicionar seu domínio ao seu locatário do Office 365, siga as etapas descritas em [Adicionar um domínio ao Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).  <br/> |
|Configurar a sincronização do Active Directory  <br/> |Sincronização do Active Directory mantém seu Active Directory local sincronizado continuamente com o Office 365. Isso permite criar versões sincronizadas de cada conta de usuário e grupo.  <br/> <br> **Importante:** Você precisa sincronizar as contas do AD do Skype todos os usuários corporativos em sua organização entre seu local e implantações online, mesmo se os usuários não são movidos para equipes ou Skype para negócios Online. Se você não sincronizar todos os usuários, a comunicação entre os usuários online e locais em sua organização poderá não funcionar como esperado. Para obter mais informações, consulte [Connect do AD de configurar o Azure para os ambientes híbridos](configure-azure-ad-connect.md).         |
| Configurar Skype para o híbrido de negócios | Há três etapas básicas: <br><br> 1. configure seu ambiente local para estabelecer uma federação com o Office 365. <br> 2. configurar seu ambiente local para confiar no Office 365 e ativar o espaço de endereçamento SIP compartilhado com o Office 365.<br> 3. Habilite o espaço de endereçamento SIP compartilhado no seu locatário do Office 365. <br><br> Além disso, se você tiver o Exchange local, em seguida, convém configurar OAuth entre o Exchange local e Skype para ambientes corporativos on-line. <br> <br>Para obter mais informações, consulte [Configurar Skype para o híbrido de negócios](configure-federation-with-skype-for-business-online.md).
|Mover usuários-piloto  <br/> |Após concluir as etapas para preparar e configurar seu ambiente para equipes ou Skype para Business Online, você pode iniciar mover usuários piloto para seu locatário do Office 365 online. Para obter mais informações, consulte [mover os usuários no local para Skype para Business Online](move-users-from-on-premises-to-skype-for-business-online.md) e [mover os usuários no local para equipes](move-users-from-on-premises-to-Teams.md).  <br/> |