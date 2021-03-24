---
title: Integracão com o Exchange e o Microsoft Office SharePoint Online
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Resumo: Saiba mais sobre a integração do Skype for Business Server 2015 com o Exchange e o SharePoint.'
ms.openlocfilehash: 01ebbdd94098fa9f7785f41fedbcbdfe7589f03e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092829"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integracão com o Exchange e o Microsoft Office SharePoint Online

**Resumo:** Saiba mais sobre a integração do Skype for Business Server 2015 com o Exchange e o SharePoint.

Você pode configurar implantações do Skype for Business Server 2015 para integração com o Microsoft Exchange Server 2016, o Microsoft Exchange Server 2013, o Microsoft Exchange Server 2010 e o SharePoint Server, no local e online. Os recursos listados na tabela a seguir são suportados com todos os clientes, a menos que especificado de outra forma. Para obter mais informações sobre o suporte ao cliente, consulte Comparação de recursos do cliente da área de trabalho [para tabelas](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) de comparação de clientes do Skype for Business e skype for Business Online em [Clients for Skype for Business Online](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

## <a name="integration-with-exchange-server"></a>Integração com Exchange Server

As tabelas a seguir listam os recursos com suporte em uma implantação híbrida quando integrados Microsoft Exchange Server.

 **Skype for Business Server local e Exchange no local**


|**Recurso**|**Anotações**|
|:-----|:-----|
|IM/Presença no Outlook  <br/> |Para obter mais informações, consulte [IM e Presence](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence).  <br/> |
|Agendar e participar de uma reunião online por meio do Outlook  <br/> |Para obter mais informações, [consulte Integrar o Skype for Business Server 2015 com Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|IM/Presença no Outlook Web App  <br/> |Para obter mais informações, [consulte Configure a hybrid environment in Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Agendar e participar de uma reunião online por meio do Outlook Web App  <br/> ||
|IM/Presença em clientes móveis  <br/> ||
|Participar de reuniões online em clientes Móveis  <br/> |Para obter mais informações, [consulte Deploying Mobility](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility).  <br/> |
|Publicar status com base em informações de livre/ocupado do calendário do Outlook  <br/> ||
|Lista de contatos (por meio do Unified Contact Store)  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> Um cliente de área de trabalho do Lync 2013 ou skype for Business é necessário.  <br/>  Para obter mais informações, [consulte Configure Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Foto de contato de alta resolução no cliente do Lync 2013, cliente skype for Business e Lync Web App.  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> Para obter mais informações, [consulte Configure the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Para fotos no aplicativo Skype for Business para MAC e Mobile, a integração entre o Skype for Business Server 2015 e o Exchange Server deve ser configurada conforme descrito em [Configure partner applications in Skype for Business Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md)e Exchange Server . <br/> |
|Delegação de reunião  <br/> |Suportado somente quando ambos os usuários estão online na mesma floresta ou ambos estão no local. Para obter mais informações, consulte [Soluções híbridas do Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Histórico de Conversas Perdidas e Logs de Chamadas são gravados na caixa de correio do exchange do usuário  <br/> ||
|Conteúdo de Arquivamento (IM e Reunião) no Exchange  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> Para obter mais informações, consulte [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Pesquisar conteúdo arquivado  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> |
|Caixa postal  <br/> |Para obter mais informações, [consulte Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail).  <br/> |

 **Skype for Business Server local e Exchange Online**


|**Recurso**|**Anotações**|
|:-----|:-----|
|IM/Presença no Outlook  <br/> |Para obter mais informações, consulte [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Agendar e participar de uma reunião online por meio do Outlook  <br/> ||
|IM/Presença no Outlook Web App  <br/> |Para obter mais informações, consulte [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Agendar e participar da reunião online do Outlook Web App  <br/> |Para obter mais informações, consulte [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|IM/Presença em Clientes Móveis  <br/> ||
|Participar de uma reunião online em clientes Móveis  <br/> ||
|Publicar status com base em informações de livre/ocupado do calendário do Outlook  <br/> ||
|Lista de contatos (por meio do Unified Contact Store).  <br/> |Somente Lync Server 2013. Um cliente de área de trabalho do Lync 2013 ou skype for Business é necessário.  <br/> Para obter mais informações, [consulte Configure Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto de contato de alta resolução no cliente do Lync 2013, cliente skype for Business e Lync Web App.  <br/> |Para obter mais informações, [consulte Configure the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Para fotos no aplicativo Skype for Business para MAC e Mobile, a integração entre o Skype for Business Server 2015 e o Exchange Server deve ser configurada conforme descrito em Configurar a integração entre o Skype for Business Server local e o [Outlook Web App.](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Delegação de reunião  <br/> |Suportado somente quando ambos os usuários estão online na mesma floresta ou ambos estão no local. Para obter mais informações, consulte [Soluções híbridas do Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Histórico de Conversas Perdidas e Logs de Chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Conteúdo de Arquivamento (IM e Reunião) no Exchange  <br/> |Para obter mais informações, consulte [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Pesquisar conteúdo arquivado  <br/> |Para obter mais informações, consulte [Configure Exchange for SharePoint eDiscovery Center](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|Caixa postal  <br/> |Para obter mais informações, consulte Fornecendo a Caixa Postal dos Usuários [do Lync Server 2013 na UM do Exchange Hospedada.](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)  <br/> |

 **Skype for Business Online e Exchange no local**


|**Recurso**|**Anotações**|
|:-----|:-----|
|Presença no Outlook  <br/> ||
|Responder via IM, Chamada PSTN, Chamada do Skype ou Chamada de Vídeo de um email do Outlook  <br/> ||
|Agendar e participar de reuniões online por meio do Outlook  <br/> ||
|IM/Presença em clientes móveis  <br/> ||
|Participar de reuniões online em clientes Móveis  <br/> ||
|Publicar status com base em informações de livre/ocupado do calendário do Outlook  <br/> ||
|Histórico de Conversas Perdidas e Logs de Chamadas são gravados na caixa de correio do exchange do usuário  <br/> ||
|Foto de contato de alta resolução no Lync 2013 ou cliente do Skype for Business.  <br/> |Requer o Exchange 2016 ou o Exchange 2013. Isso não é suportado no Lync Web App quando os usuários estão em casa no Skype for Business Online.  <br/> |
|Delegação de reunião  <br/> |Suportado somente quando ambos os usuários estão online na mesma floresta ou ambos estão no local. Para obter mais informações, consulte [Soluções híbridas do Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Histórico de Conversas Perdidas e Logs de Chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Histórico da Conversa do Lado do Servidor  <br/> ||

 **Skype for Business Online e Exchange Online**


|**Recurso**|**Anotações**|
|:-----|:-----|
|IM/Presença no Outlook  <br/> ||
|Agendar e participar de reuniões online por meio do Outlook  <br/> ||
|IM/Presença no Outlook Web App  <br/> ||
|Agendar e participar da reunião online do Outlook Web App  <br/> ||
|IM/Presença em Clientes Móveis  <br/> ||
|Participar de uma reunião online em clientes Móveis  <br/> ||
|Publicar status com base em informações de livre/ocupado do calendário do Outlook  <br/> ||
|Histórico de Conversas Perdidas e Logs de Chamadas são gravados na caixa de correio do exchange do usuário  <br/> ||
|Lista de contatos (por meio do Unified Contact Store)  <br/> |Lync Server 2013 ou cliente skype for Business necessário  <br/> |
|Foto de contato de alta resolução no Lync 2013, cliente do Skype for Business e Lync Web App  <br/> ||
|Delegação de reunião  <br/> |Suportado somente quando ambos os usuários estão online na mesma floresta ou ambos estão no local. Para obter mais informações, consulte [Soluções híbridas do Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Conteúdo de Arquivamento (IM e Reunião) no Exchange  <br/> ||
|Pesquisar conteúdo arquivado  <br/> ||
|Caixa postal  <br/> ||

## <a name="integration-with-sharepoint"></a>Integração com o SharePoint

A tabela a seguir lista os recursos com suporte em uma implantação híbrida quando integrados ao SharePoint.

||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 local** <br/> | Pesquisa de habilidades <br/>  Presença no SharePoint <br/> | Presença no SharePoint <br/> |
|**Skype for Business Online** <br/> | Presença no SharePoint <br/> | Presença no SharePoint <br/> |