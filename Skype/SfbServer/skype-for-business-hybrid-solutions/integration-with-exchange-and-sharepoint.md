---
title: Integração com o Exchange e o SharePoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
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
ms.openlocfilehash: 18839125faee2dfd27ad3843e37b723f56581ff3
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231142"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integração com o Exchange e o SharePoint

**Resumo:** Saiba mais sobre a integração do Skype for Business Server 2015 com o Exchange e o SharePoint.

Você pode configurar as implantações do Skype for Business Server 2015 para integração com o Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 e SharePoint Server, tanto local quanto online. Os recursos listados na tabela a seguir têm suporte em todos os clientes, a menos que haja uma especificação diferente. Para obter mais informações sobre o suporte ao cliente, consulte [comparação de recursos do cliente de área de trabalho para](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) as tabelas de comparação de clientes do Skype for Business e do Skype for Business online em [clientes para o Skype for Business online](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Integração com o Exchange Server

As tabelas a seguir listam os recursos com suporte em uma implantação híbrida quando integrado ao Microsoft Exchange Server.

 **Skype for Business Server local e Exchange local**


|**Recurso**|**Observações**|
|:-----|:-----|
|IM/presença no Outlook  <br/> |Para obter mais informações, consulte [mensagens instantâneas e presença](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Agende e participe de reuniões online via Outlook  <br/> |Para obter mais informações, consulte [integrar o Skype for Business Server 2015 com o Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Mensagem instantânea/presença no Outlook Web App  <br/> |Para obter mais informações, consulte [configurar um ambiente híbrido no Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Agendar e ingressar em reunião online por meio do Outlook Web App  <br/> ||
|IM/Presença em clientes de dispositivos móveis  <br/> ||
|Participe de reuniões online em clientes de dispositivos móveis  <br/> |Para obter mais informações, consulte [implantando a mobilidade](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Publique o status com base nas informações de ocupado/livre do calendário do Outlook  <br/> ||
|Lista de contatos (via repositório de contato unificado)  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> É necessário um cliente de desktop do Lync 2013 ou Skype for Business.  <br/>  Para obter mais informações, consulte [Configurar o Skype for Business Server 2015 para usar o repositório de contatos unificado](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Foto de contato de alta resolução no cliente do Lync 2013, cliente Skype for Business e Lync Web App.  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> Para obter mais informações, consulte [Configurar o uso de fotos de alta resolução no Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Para fotos no aplicativo Skype for Business para MAC e celular, a integração entre o Skype for Business Server 2015 e o Exchange Server deve ser configurada conforme descrito em [configurar aplicativos de parceiro no Skype for Business Server e no Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Delegação da reunião  <br/> |Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local. Para obter mais informações, consulte [soluções híbridas do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Histórico de conversas perdidas e logs de chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> Para obter mais informações, consulte [lista de verificação de implantação para arquivamento](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Pesquise o conteúdo arquivado  <br/> |Requer o Exchange 2016 ou o Exchange 2013.  <br/> |
|Caixa postal  <br/> |Para obter mais informações, consulte [implantando o Exchange um local para fornecer correio de voz do Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype for Business Server no local e Exchange Online**


|**Recurso**|**Observações**|
|:-----|:-----|
|IM/presença no Outlook  <br/> |Para obter mais informações, consulte [Configurar a integração entre o Skype for Business Server 2015 local e o Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Agende e participe de reuniões online via Outlook  <br/> ||
|Mensagem instantânea/presença no Outlook Web App  <br/> |Para obter mais informações, consulte [Configurar a integração entre o Skype for Business Server 2015 local e o Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Agendar e ingressar em reunião online a partir do Outlook Web App  <br/> |Para obter mais informações, consulte [Configurar a integração entre o Skype for Business Server 2015 local e o Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|IM/Presença em clientes de dispositivos móveis  <br/> ||
|Participe de uma reunião online em clientes de dispositivos móveis  <br/> ||
|Publique o status com base nas informações de ocupado/livre do calendário do Outlook  <br/> ||
|Lista de contatos (via repositório de contato unificado).  <br/> |Somente Lync Server 2013. É necessário um cliente de desktop do Lync 2013 ou Skype for Business.  <br/> Para obter mais informações, consulte [Configurar o Skype for Business Server 2015 para usar o repositório de contatos unificado](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto de contato de alta resolução no cliente do Lync 2013, cliente Skype for Business e Lync Web App.  <br/> |Para obter mais informações, consulte [Configurar o uso de fotos de alta resolução no Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Para fotos no aplicativo Skype for Business para MAC e celular, a integração entre o Skype for Business Server 2015 e o Exchange Server deve ser configurada conforme descrito em [Configurar a integração entre o Skype for Business Server local e o Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Delegação da reunião  <br/> |Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local. Para obter mais informações, consulte [soluções híbridas do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Histórico de conversas perdidas e logs de chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> |Para obter mais informações, consulte [lista de verificação de implantação para arquivamento](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Pesquise o conteúdo arquivado  <br/> |Para obter mais informações, consulte em [Configurar o centro de descoberta automática do Exchange para SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Caixa postal  <br/> |Para obter mais informações, consulte [fornecendo aos usuários do Lync Server 2013 o correio de voz no Exchange um hospedado](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype for Business Online e Exchange local**


|**Recurso**|**Observações**|
|:-----|:-----|
|Presença no Outlook  <br/> ||
|Responder via IM, Chamada PSTN, Chamada do Skype ou Chamada de Vídeo a partir de um email do Outlook  <br/> ||
|Agende e participe de reuniões online via Outlook  <br/> ||
|IM/Presença em clientes de dispositivos móveis  <br/> ||
|Participe de reuniões online em clientes de dispositivos móveis  <br/> ||
|Publique o status com base nas informações de ocupado/livre do calendário do Outlook  <br/> ||
|Histórico de conversas perdidas e logs de chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Foto de contato de alta resolução no Lync 2013 ou no cliente Skype for Business.  <br/> |Requer o Exchange 2016 ou o Exchange 2013. Isso não é compatível com o Lync Web App quando os usuários são hospedados no Skype for Business online.  <br/> |
|Delegação da reunião  <br/> |Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local. Para obter mais informações, consulte [soluções híbridas do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Histórico de conversas perdidas e logs de chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Histórico da Conversa no Lado do Servidor  <br/> ||

 **Skype for Business Online e Exchange Online**


|**Recurso**|**Observações**|
|:-----|:-----|
|IM/presença no Outlook  <br/> ||
|Agende e participe de reuniões online via Outlook  <br/> ||
|Mensagem instantânea/presença no Outlook Web App  <br/> ||
|Agendar e ingressar em reunião online a partir do Outlook Web App  <br/> ||
|IM/Presença em clientes de dispositivos móveis  <br/> ||
|Participe de uma reunião online em clientes de dispositivos móveis  <br/> ||
|Publique o status com base nas informações de ocupado/livre do calendário do Outlook  <br/> ||
|Histórico de conversas perdidas e logs de chamadas são gravados na caixa de correio do Exchange do usuário  <br/> ||
|Lista de contatos (via repositório de contato unificado)  <br/> |É necessário o Lync Server 2013 ou o cliente Skype for Business  <br/> |
|Foto de contato de alta resolução no Lync 2013, cliente Skype for Business e Lync Web App  <br/> ||
|Delegação da reunião  <br/> |Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local. Para obter mais informações, consulte [soluções híbridas do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> ||
|Pesquise o conteúdo arquivado  <br/> ||
|Caixa postal  <br/> ||

## <a name="integration-with-sharepoint"></a>Integração com SharePoint

A tabela a seguir lista os recursos com suporte em uma implantação híbrida quando integrado ao SharePoint.

||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 local** <br/> | Pesquisa de habilidades <br/>  Presença no SharePoint <br/> | Presença no SharePoint <br/> |
|**Skype for Business Online** <br/> | Presença no SharePoint <br/> | Presença no SharePoint <br/> |


