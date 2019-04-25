---
title: Obter telefones para o Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 91f2d947-45fc-4fab-bd8b-2e313531c477
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba quais telefones da Polycom, HP, and Mitel funcionam com o Skype for Business e as licenças necessárias. '
ms.openlocfilehash: e79c942923e9a9d4d0df0bc18172eb10caff57bc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229521"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obter telefones para o Skype for Business Online

Skype for Business Online qualifies and supports desktop phones for users who want to have a traditional phone experience, rather than use the Skype for Business app. This topic covers the phones and firmware versions that are supported for use in Skype for Business Online and other information that can help you when you are setting up phones in your organization.
  
Para obter as atualizações mais recentes e a maioria das informações atualizadas sobre os dispositivos suportados, consulte o [Skype para catálogo de dispositivo corporativos](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
## <a name="supported-phones"></a>Telefones compatíveis

Para Skype para usuários corporativos Online, você poderá escolher entre vários modelos dentro do *certificado para Skype para telefones de negócios* e telefones executando a edição de telefone do Lync (LPE) listado sob o Skype para a categoria Business Online no [Skype para o dispositivo de negócios Catálogo](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
Microsoft é parceria e trabalhando em conjunto com o Polycom, Yealink e AudioCodes para desenvolver e certificar a uma ampla variedade de dispositivos por meio de parceiro IP Phone programa (PIP) para o sistema telefônico no Office 365 e Skype para Business Server.
  
When ordering new phones for Skype for Business, it is important to buy phones with the *right product ID*. These product IDs will ensure that the phones you receive have the Skype for Business Online qualified version already installed.
  
|||
|:-----|:-----|
|**Parceiro de Telefone** <br/> |**ID do produto específico para o Skype for Business** <br/> |
|Polycom  <br/> |ID do Produto -019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Para obter mais detalhes sobre os telefones Polycom, veja [Soluções de voz para Microsoft](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
  
Para obter mais detalhes sobre os telefones Yealink, veja [Telefones IP do Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Para obter mais detalhes em AudioCodes telefones, consulte [Skype para telefones IP de negócios](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Phone Edition is supported with Skype for Business Online, but not with Microsoft Teams. Mainstream support for the LPE platform ended by April/10/2014, with extended support until April/11/2023 to align with the product support lifecycle of Lync Server 2013. See [Microsoft Product Lifecycle](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) for details on the LPE lifecycle. LPE CAP models aren't supported with Skype for Business Online.
>
> Later this year, Office 365 will not support any version of TLS older than 1.2. Since the underlying operating system of LPE does not support TLS 1.2, LPE will not be supported to connect to Office 365 anymore. See [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365) for more information.
  
## <a name="supported-firmware"></a>Com suporte do firmware

Esta é a versão mínima de software necessária para telefones compatíveis trabalharem com o Sistema de Telefonia no Office 365:
  
||||
|:-----|:-----|:-----|
|**Tipo de telefone** <br/> |**Firmware mínimo** <br/> |**Data de lançamento** <br/> |
|Otimizado (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Maio 2015  <br/> |
|Série VVX Polycom Certificada  <br/> |5.4.0A  <br/> |Dezembro de 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Fevereiro de 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Dezembro de 2016  <br/> |

Para obter mais detalhes sobre as versões atuais do firmware de certificados, consulte [Skype para telefones IP de negócios](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones#conference-phones).

> [!NOTE]
> [!OBSERVAçãO] Os telefones Lync Phone Edition (LPE) configurados para sua implantação local devem ser atualizados para o firmware mínimo ou superior necessário antes de você mover esses usuários para o Skype for Business Online. Se você mover os usuários locais para o Skype for Business Online antes de atualizar o firmware nos telefones, esses telefones não poderão conectar-se ao Skype for Business Online. 
  
## <a name="required-licenses"></a>Licenças necessárias

Skype para Business Online não exige qualquer licença da Microsoft adicional que não seja as licenças de usuário. Para saber mais sobre as licenças de usuário necessárias, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Modelos de licenciamento do fabricante pode variar entre open SIP e Skype para negócios Certified firmware. Se você estiver reorientando um modelo de certificado com um firmware de SIP aberto, deverá verificar os requisitos de licenciamento do firmware com o fabricante.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype para o conjunto de recursos de telefones corporativos Online conectados

Para o dispositivo completo de recursos e capacidades, verifique os guias de usuário do fabricante.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Recurso** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPE** <br/> |
|Entre com as credenciais dos usuários  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Entrar via PC (Emparelhamento), somente Windows  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Entrar usando (Entrada na Web)  <br/>  <br/> **Observação:** Verifique a matriz de suporte no guia de implantação.           |Sim  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Clique único para ingressar na reunião  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Clique para discar (Emparelhamento)  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Controles de reunião  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Caixa postal visual  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Trava de telefone  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Atualização de dispositivo  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Provisionamento em banda  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|QoE  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Upload de log  <br/> <br/> **Observação:** Atualmente, todos os logs são carregados para a equipe do Microsoft Support apenas; acesso de cliente aos logs de telefone não ainda estarão disponíveis.           |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Autenticação moderna  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Vários Números de Emergência  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |Sim  <br/> |
|Integração com o calendário do Exchange*  <br/> |Sim  <br/> |Sim  <br/> |Sim   <br/> |Sim  <br/> <br/> **Observação:** Requer PC tethering           |
|Integração de presença  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Diretório Corporativo  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Delegação  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Integração da imagem do contato  <br/> |Não  <br/> |Sim  <br/> |Não  <br/> |Sim  <br/> |
||||||

     
> [!NOTE]
> CX 600 ou quaisquer outros telefones Aries não oferecem suporte a autenticação multifator (MFA). Se você forçar MFA, esses dispositivos não poderão se conectar. Esses dispositivos devem usar somente ID da organização para autenticação.
 
## <a name="what-else-should-you-know"></a>O que mais você deve saber?
Para obter instruções de configuração passo a passo, veja [Implantar telefones para o Skype for Business Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Tópicos relacionados
[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](../getting-service-phone-numbers.md)

[Veja aqui o que você obtém com o Sistema de Telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
