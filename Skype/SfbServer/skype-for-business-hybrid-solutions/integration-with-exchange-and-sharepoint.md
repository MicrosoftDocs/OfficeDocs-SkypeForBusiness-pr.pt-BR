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
description: 'Resumo: saiba mais sobre a integração do Skype for Business Server 2015 com o Exchange e o SharePoint.'
ms.openlocfilehash: 943392fbd63238621825edad380ac9c140935635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821101"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integracão com o Exchange e o Microsoft Office SharePoint Online

**Resumo:** Saiba mais sobre a integração do Skype for Business Server 2015 com o Exchange e o SharePoint.

Você pode configurar implantações do Skype for Business Server 2015 para integração com o Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 e SharePoint Server, no local e online. Os recursos listados na tabela a seguir são suportados com todos os clientes, a menos que especificado de outra forma. Para obter mais informações sobre o suporte ao cliente, consulte Comparação de recursos do cliente de área de trabalho para tabelas de comparação de clientes do [Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) e do Skype for Business Online no Clients for Skype for Business [Online.](https://go.microsoft.com/fwlink/p/?LinkId=281902)

## <a name="integration-with-exchange-server"></a>Integração com o Exchange Server

As tabelas a seguir listam os recursos com suporte em uma implantação híbrida quando integrados ao Microsoft Exchange Server.

 **Skype for Business Server local e Exchange no local**


|**Característica**|**Anotações**|
|:-----|:-----|
|IM/Presença no Outlook  <br/> |Para obter mais informações, consulte [IM e Presença.](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)  <br/> |
|Agendar e participar de uma reunião online por meio do Outlook  <br/> |Para obter mais informações, consulte [Integrar o Skype for Business Server 2015 com o Exchange Server.](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|IM/Presença no Outlook Web App  <br/> |Para obter mais informações, [consulte Configurar um ambiente híbrido no Skype for Business Server 2015.](../manage/authentication/configure-a-hybrid-environment.md)  <br/> |
|Agendar e participar de uma reunião online por meio do Outlook Web App  <br/> ||
|IM/Presença em clientes móveis  <br/> ||
|Ingressar em reuniões online em clientes móveis  <br/> |Para obter mais informações, [consulte Implantando mobilidade](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Publicar status com base nas informações de livre/ocupado do calendário do Outlook  <br/> ||
|Lista de contatos (por meio do Armazenamento unificado de contatos)  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> É necessário ter um cliente de área de trabalho do Lync 2013 ou do Skype for Business.  <br/>  Para obter mais informações, [consulte Configurar o Skype for Business Server 2015 para usar o armazenamento unificado de contatos.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)  <br/> |
|Foto de contato de alta resolução no cliente do Lync 2013, no cliente Skype for Business e no Lync Web App.  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> Para obter mais informações, consulte Configurar o uso de fotos em alta [resolução no Skype for Business Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Para fotos no aplicativo Skype for Business para MAC e Mobile, a integração entre o Skype for Business Server 2015 e o Exchange Server deve ser configurada conforme descrito em Configurar aplicativos parceiros no Skype for Business Server e no [Exchange Server.](../deploy/integrate-with-exchange-server/configure-partner-applications.md) <br/> |
|Delegação de reunião  <br/> |Suportado somente quando ambos os usuários estão online na mesma floresta ou ambos estão no local. Para saber mais, confira [Soluções híbridas do Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|O histórico de Conversas Perdidas e os Logs de Chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> Para obter mais informações, [consulte Lista de verificação de implantação para arquivamento.](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)  <br/> |
|Pesquisar conteúdo arquivado  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> |
|Caixa postal  <br/> |Para obter mais informações, [consulte Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype for Business Server local e Exchange Online**


|**Característica**|**Anotações**|
|:-----|:-----|
|IM/Presença no Outlook  <br/> |Para obter mais informações, consulte Configurar a integração entre o [Skype for Business Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) local e o Outlook Web App <br/> |
|Agendar e participar de uma reunião online por meio do Outlook  <br/> ||
|IM/Presença no Outlook Web App  <br/> |Para obter mais informações, consulte Configurar a integração entre o [Skype for Business Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) local e o Outlook Web App <br/> |
|Agendar e participar de uma reunião online do Outlook Web App  <br/> |Para obter mais informações, consulte Configurar a integração entre o [Skype for Business Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md) local e o Outlook Web App <br/> |
|IM/presença em clientes móveis  <br/> ||
|Ingressar em uma reunião online em clientes móveis  <br/> ||
|Publicar status com base nas informações de livre/ocupado do calendário do Outlook  <br/> ||
|Lista de contatos (por meio do Armazenamento unificado de contatos).  <br/> |Somente Lync Server 2013. É necessário ter um cliente de área de trabalho do Lync 2013 ou do Skype for Business.  <br/> Para obter mais informações, [consulte Configurar o Skype for Business Server 2015 para usar o armazenamento unificado de contatos](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto de contato de alta resolução no cliente do Lync 2013, no cliente Skype for Business e no Lync Web App.  <br/> |Para obter mais informações, consulte Configurar o uso de fotos em alta [resolução no Skype for Business Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Para fotos no aplicativo Skype for Business para MAC e Mobile, a integração entre o Skype for Business Server 2015 e o Exchange Server deve ser configurada conforme descrito em Configurar a integração entre o Skype for Business Server local e o [Outlook Web App.](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Delegação de reunião  <br/> |Suportado somente quando ambos os usuários estão online na mesma floresta ou ambos estão no local. Para saber mais, confira [Soluções híbridas do Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|O histórico de Conversas Perdidas e Os Logs de Chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> |Para obter mais informações, [consulte Lista de verificação de implantação para arquivamento.](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)  <br/> |
|Pesquisar conteúdo arquivado  <br/> |Para obter mais informações, consulte [Configurar o Exchange para o Centro de Descobertas e Descobertas Do SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Caixa postal  <br/> |Para obter mais informações, [consulte Providing Lync Server 2013 Users Voice Mail on Hosted Exchange UM](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype for Business Online e Exchange no local**


|**Característica**|**Anotações**|
|:-----|:-----|
|Presença no Outlook  <br/> ||
|Responder via IM, Chamada PSTN, Chamada do Skype ou Chamada de Vídeo de um email do Outlook  <br/> ||
|Agendar e participar de reuniões online por meio do Outlook  <br/> ||
|IM/Presença em clientes móveis  <br/> ||
|Ingressar em reuniões online em clientes móveis  <br/> ||
|Publicar status com base nas informações de livre/ocupado do calendário do Outlook  <br/> ||
|O histórico de Conversas Perdidas e os Logs de Chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Foto de contato de alta resolução no cliente do Lync 2013 ou do Skype for Business.  <br/> |Requer o Exchange 2016 ou o Exchange 2013. Isso não é suportado no Lync Web App quando os usuários estão no Skype for Business Online.  <br/> |
|Delegação de reunião  <br/> |Suportado somente quando ambos os usuários estão online na mesma floresta ou ambos estão no local. Para saber mais, confira [Soluções híbridas do Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|O histórico de Conversas Perdidas e Os Logs de Chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Histórico de conversas do lado do servidor  <br/> ||

 **Skype for Business Online e Exchange Online**


|**Característica**|**Anotações**|
|:-----|:-----|
|IM/Presença no Outlook  <br/> ||
|Agendar e participar de reuniões online por meio do Outlook  <br/> ||
|IM/Presença no Outlook Web App  <br/> ||
|Agendar e participar de uma reunião online do Outlook Web App  <br/> ||
|IM/presença em clientes móveis  <br/> ||
|Ingressar em uma reunião online em clientes móveis  <br/> ||
|Publicar status com base nas informações de livre/ocupado do calendário do Outlook  <br/> ||
|O histórico de Conversas Perdidas e os Logs de Chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Lista de contatos (por meio do Armazenamento unificado de contatos)  <br/> |Lync Server 2013 ou cliente Skype for Business necessário  <br/> |
|Foto de contato de alta resolução no Lync 2013, no cliente Skype for Business e no Lync Web App  <br/> ||
|Delegação de reunião  <br/> |Suportado somente quando ambos os usuários estão online na mesma floresta ou ambos estão no local. Para saber mais, confira [Soluções híbridas do Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> ||
|Pesquisar conteúdo arquivado  <br/> ||
|Caixa postal  <br/> ||

## <a name="integration-with-sharepoint"></a>Integração com o SharePoint

A tabela a seguir lista os recursos com suporte em uma implantação híbrida quando integrados ao SharePoint.

||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 local** <br/> | Pesquisa de habilidades <br/>  Presença no SharePoint <br/> | Presença no SharePoint <br/> |
|**Skype for Business Online** <br/> | Presença no SharePoint <br/> | Presença no SharePoint <br/> |


