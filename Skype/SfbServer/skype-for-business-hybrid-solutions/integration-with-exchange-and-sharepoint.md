---
title: Integração com o Exchange e SharePoint
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 'Resumo: Saiba mais sobre Skype para integração de Business Server 2015 com o Exchange e SharePoint.'
ms.openlocfilehash: 8d080174ab5560384478c1320d09bc218ef8543b
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839209"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integração com o Exchange e SharePoint

**Resumo:** Saiba mais sobre Skype para integração de Business Server 2015 com o Exchange e SharePoint.

Você pode configurar Skype para implantações de negócios Server 2015 para integração com o Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 e SharePoint Server, tanto no local e online. Os recursos listados na tabela a seguir têm suporte em todos os clientes, a menos que haja uma especificação diferente. Para obter mais informações sobre o cliente suporte, consulte a [comparação de recursos do cliente de Desktop do Skype para negócios](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) e Skype para tabelas de comparação de cliente Business Online em [clientes do Skype para negócios Online](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Integração com o Exchange Server

As tabelas a seguir listam os recursos suportados em uma implantação híbrida quando integrado ao Microsoft Exchange Server.

 **Skype para Business Server no local e do Exchange no local**


|**Recurso**|**Observações**|
|:-----|:-----|
|IM/presença no Outlook  <br/> |Para obter mais informações, consulte [IM e presença](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Agende e participe de reuniões online via Outlook  <br/> |Para obter mais informações, consulte [Integrar Skype para 2015 do servidor de negócios com o Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|IM/presença no Outlook Web App  <br/> |Para obter mais informações, consulte [Configure um ambiente híbrido do Skype para Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Agendamento e participação de reunião online por meio do Outlook Web App  <br/> ||
|IM/Presença em clientes de dispositivos móveis  <br/> ||
|Participe de reuniões online em clientes de dispositivos móveis  <br/> |Para obter mais informações, consulte [Implantação de mobilidade](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Publique o status com base nas informações de ocupado/livre do calendário do Outlook  <br/> ||
|Lista de contatos (via repositório de contato unificado)  <br/> |Exige 2016 do Exchange ou o Exchange 2013.  <br/> É necessário um Lync 2013 ou Skype para o cliente de desktop de negócios.  <br/>  Para obter mais informações, consulte [Configurar Skype para negócios 2015 de servidor usar o repositório unificado de contatos](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Foto de alta resolução contato no cliente do Lync 2013, Skype para o cliente de negócios e Lync Web App.  <br/> |Exige 2016 do Exchange ou o Exchange 2013.  <br/> Para obter mais informações, consulte [Configurar o uso de fotos de alta resolução no Skype para Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> |
|Delegação da reunião  <br/> |Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local. Para obter mais informações, consulte [Skype para soluções híbridas de negócios](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Perdidas histórico de conversas e Logs de chamada são gravados de correio do exchange do usuário  <br/> ||
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> |Exige 2016 do Exchange ou o Exchange 2013.  <br/> Para obter mais informações, consulte a [Lista de verificação de implantação para arquivamento](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Pesquise o conteúdo arquivado  <br/> |Exige 2016 do Exchange ou o Exchange 2013.  <br/> |
|Caixa postal  <br/> |Para obter mais informações, consulte [Implantando local UM do Exchange para fornecer a correio de voz do Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype para Business Server no local e o Exchange Online**


|**Recurso**|**Observações**|
|:-----|:-----|
|IM/presença no Outlook  <br/> |Para obter mais informações, consulte [Configure de integração entre o local Skype para Business Server 2015 e Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Agende e participe de reuniões online via Outlook  <br/> ||
|IM/presença no Outlook Web App  <br/> |Para obter mais informações, consulte [Configure de integração entre o local Skype para Business Server 2015 e Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Agendamento e participação de reunião online do Outlook Web App  <br/> |Para obter mais informações, consulte [Configure de integração entre o local Skype para Business Server 2015 e Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|IM/Presença em clientes de dispositivos móveis  <br/> ||
|Participe de uma reunião online em clientes de dispositivos móveis  <br/> ||
|Publique o status com base nas informações de ocupado/livre do calendário do Outlook  <br/> ||
|Lista de contatos (via repositório de contato unificado).  <br/> |Lync Server 2013 apenas. É necessário um Lync 2013 ou Skype para o cliente de desktop de negócios.  <br/> Para obter mais informações, consulte [Configurar Skype para negócios 2015 de servidor usar o repositório unificado de contatos](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto de alta resolução contato no cliente do Lync 2013, Skype para o cliente de negócios e Lync Web App.  <br/> |Para obter mais informações, consulte [Configurar o uso de fotos de alta resolução no Skype para Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> |
|Delegação da reunião  <br/> |Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local. Para obter mais informações, consulte [Skype para soluções híbridas de negócios](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Perdidas histórico de conversas e Logs de chamada são gravados de correio do Exchange do usuário  <br/> ||
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> |Para obter mais informações, consulte a [Lista de verificação de implantação para arquivamento](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Pesquise o conteúdo arquivado  <br/> |Para obter mais informações, consulte [Configurar o Exchange para o SharePoint eDiscovery Center](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Caixa postal  <br/> |Para obter mais informações, consulte [Fornecendo Lync Server 2013 caixa postal aos usuários no hospedado UM do Exchange](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype para Business Online e do Exchange no local**


|**Recurso**|**Observações**|
|:-----|:-----|
|Presença no Outlook  <br/> ||
|Responder via IM, Chamada PSTN, Chamada do Skype ou Chamada de Vídeo a partir de um email do Outlook  <br/> ||
|Agende e participe de reuniões online via Outlook  <br/> ||
|IM/Presença em clientes de dispositivos móveis  <br/> ||
|Participe de reuniões online em clientes de dispositivos móveis  <br/> ||
|Publique o status com base nas informações de ocupado/livre do calendário do Outlook  <br/> ||
|Perdidas histórico de conversas e Logs de chamada são gravados de correio do exchange do usuário  <br/> ||
|Foto de alta resolução contatos no Lync 2013 ou Skype para o cliente de negócios.  <br/> |Exige 2016 do Exchange ou o Exchange 2013. Isso não é suportado no Lync Web App quando os usuários hospedados no Skype para negócios Online.  <br/> |
|Delegação da reunião  <br/> |Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local. Para obter mais informações, consulte [Skype para soluções híbridas de negócios](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Perdidas histórico de conversas e Logs de chamada são gravados de correio do Exchange do usuário  <br/> ||
|Histórico da Conversa no Lado do Servidor  <br/> ||

 **Skype para negócios on-line e no Exchange Online**


|**Recurso**|**Observações**|
|:-----|:-----|
|IM/presença no Outlook  <br/> ||
|Agende e participe de reuniões online via Outlook  <br/> ||
|IM/presença no Outlook Web App  <br/> ||
|Agendamento e participação de reunião online do Outlook Web App  <br/> ||
|IM/Presença em clientes de dispositivos móveis  <br/> ||
|Participe de uma reunião online em clientes de dispositivos móveis  <br/> ||
|Publique o status com base nas informações de ocupado/livre do calendário do Outlook  <br/> ||
|Perdidas histórico de conversas e Logs de chamada são gravados de correio do exchange do usuário  <br/> ||
|Lista de contatos (via repositório de contato unificado)  <br/> |Lync Server 2013 ou Skype para o cliente de negócios necessário  <br/> |
|Foto de alta resolução contatos no Lync 2013, Skype para o cliente de negócios e Lync Web App  <br/> ||
|Delegação da reunião  <br/> |Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local. Para obter mais informações, consulte [Skype para soluções híbridas de negócios](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> ||
|Pesquise o conteúdo arquivado  <br/> ||
|Caixa postal  <br/> ||

## <a name="integration-with-sharepoint"></a>Integração com SharePoint

A tabela a seguir lista os recursos com suporte em uma implantação híbrida quando integrado com o SharePoint.

||**SharePoint local**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype para Business Server 2015 local** <br/> | Pesquisa de habilidades <br/>  Presença no SharePoint <br/> | Presença no SharePoint <br/> |
|**Skype for Business Online** <br/> | Presença no SharePoint <br/> | Presença no SharePoint <br/> |


