---
title: Integracão com o Exchange e o Microsoft Office SharePoint Online
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Resumo: saiba mais sobre Skype for Business Server integração 2015 com Exchange e SharePoint.'
ms.openlocfilehash: b599567742cf55d43c1c20c0efcce07a88c86d6c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863188"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integracão com o Exchange e o Microsoft Office SharePoint Online

**Resumo:** Saiba mais sobre Skype for Business Server integração 2015 com Exchange e SharePoint.

Você pode configurar as implantações do Skype for Business Server 2015 para integração com o Microsoft Exchange Server 2016, o Microsoft Exchange Server 2013, o Microsoft Exchange Server 2010 e o SharePoint Server, no local e online. Os recursos listados na tabela a seguir são suportados com todos os clientes, a menos que especificado de outra forma. Para obter mais informações sobre o suporte ao cliente, consulte Comparação de recursos do cliente de área de trabalho [para Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) e Skype for Business tabelas de comparação de cliente online em Clients for [Skype for Business Online](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>Integração com Exchange Server

As tabelas a seguir listam os recursos com suporte em uma implantação híbrida quando integrados Microsoft Exchange Server.

 **Skype for Business Server local e Exchange local**


|**Característica**|**Anotações**|
|:-----|:-----|
|IM/Presença no Outlook  <br/> |Para obter mais informações, consulte [IM e Presence](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence).  <br/> |
|Agendar e participar da reunião online por meio Outlook  <br/> |Para obter mais informações, consulte [Integrar Skype for Business Server 2015 com Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|IM/Presença no Outlook Web App  <br/> |Para obter mais informações, [consulte Configure a hybrid environment in Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Agendar e participar da reunião online por meio Outlook Web App  <br/> ||
|IM/Presença em clientes móveis  <br/> ||
|Participar de reuniões online em clientes Móveis  <br/> |Para obter mais informações, [consulte Deploying Mobility](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility).  <br/> |
|Publicar status com base em Outlook de agenda livre/ocupado  <br/> ||
|Lista de contatos (por meio do Unified Contact Store)  <br/> |Requer Exchange 2016 ou Exchange 2013.  <br/> Um cliente da área de trabalho do Lync 2013 ou Skype for Business é necessário.  <br/>  Para obter mais informações, [consulte Configure Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Foto de contato de alta resolução no cliente do Lync 2013, Skype for Business cliente e Lync Web App.  <br/> |Requer Exchange 2016 ou Exchange 2013.  <br/> Para obter mais informações, [consulte Configure the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Para fotos no aplicativo Skype for Business para MAC e Mobile, a integração entre o Skype for Business Server 2015 e o Exchange Server deve ser configurada conforme descrito em [Configure partner applications in Skype for Business Server and Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Delegação de reunião  <br/> |Suportado somente quando ambos os usuários estão online na mesma floresta ou ambos estão no local. Para obter mais informações, consulte [Configure hybrid connectivity between Skype for Business Server and Teams](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md). <br/> |
|Histórico de Conversas Perdidas e Logs de Chamadas são gravados na caixa de correio do exchange do usuário  <br/> ||
|Conteúdo de Arquivamento (IM e Reunião) em Exchange  <br/> |Requer Exchange 2016 ou Exchange 2013.  <br/> Para obter mais informações, consulte [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Pesquisar conteúdo arquivado  <br/> |Requer Exchange 2016 ou Exchange 2013.  <br/> |
|Caixa postal  <br/> |Para obter mais informações, consulte [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail).  <br/> |

 **Skype for Business Server local e Exchange Online**


|**Característica**|**Anotações**|
|:-----|:-----|
|IM/Presença no Outlook  <br/> |Para obter mais informações, consulte [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Agendar e participar da reunião online por meio Outlook  <br/> ||
|IM/Presença no Outlook Web App  <br/> |Para obter mais informações, consulte [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Agendar e participar da reunião online Outlook Web App  <br/> |Para obter mais informações, consulte [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|IM/Presença em Clientes Móveis  <br/> ||
|Participar de uma reunião online em clientes Móveis  <br/> ||
|Publicar status com base em Outlook de agenda livre/ocupado  <br/> ||
|Lista de contatos (por meio do Unified Contact Store).  <br/> |Somente Lync Server 2013. Um cliente da área de trabalho do Lync 2013 ou Skype for Business é necessário.  <br/> Para obter mais informações, [consulte Configure Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto de contato de alta resolução no cliente do Lync 2013, Skype for Business cliente e Lync Web App.  <br/> |Para obter mais informações, [consulte Configure the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Para fotos no aplicativo Skype for Business MAC e Mobile, a integração entre o Skype for Business Server 2015 e o Exchange Server deve ser configurada conforme descrito em Configure integration between [on-premises Skype for Business Server and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Delegação de reunião  <br/> |Suportado somente quando ambos os usuários estão online na mesma floresta ou ambos estão no local. Para obter mais informações, [consulte Skype for Business soluções híbridas.](/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Histórico de Conversas Perdidas e Logs de Chamadas são gravados na caixa de correio Exchange usuário  <br/> ||
|Conteúdo de Arquivamento (IM e Reunião) em Exchange  <br/> |Para obter mais informações, consulte [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Pesquisar conteúdo arquivado  <br/> |Para obter mais informações, consulte [Configure Exchange for SharePoint eDiscovery Center](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|Caixa postal  <br/> |Para obter mais informações, consulte Fornecendo a Caixa Postal dos Usuários do [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)na UM Exchange um .  <br/> |


## <a name="integration-with-sharepoint"></a>Integração com SharePoint

A tabela a seguir lista os recursos com suporte em uma implantação híbrida quando integrados SharePoint.

||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 local** <br/> | Pesquisa de habilidades <br/>  Presença no SharePoint <br/> | Presença no SharePoint <br/> |
|**Skype for Business Online** <br/> | Presença no SharePoint <br/> | Presença no SharePoint <br/> |
