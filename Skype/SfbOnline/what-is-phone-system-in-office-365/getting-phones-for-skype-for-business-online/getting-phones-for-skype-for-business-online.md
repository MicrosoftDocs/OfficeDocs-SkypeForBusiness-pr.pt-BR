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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba quais telefones da Polycom, HP, and Mitel funcionam com o Skype for Business e as licenças necessárias. '
ms.openlocfilehash: 92a91d97efabeaaebb074e41e41bc9a8812fa0c5
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780605"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obter telefones para o Skype for Business Online

O Skype for Business Online qualifica e é compatível com telefones de mesa para usuários que desejam uma experiência com um telefone convencional ao usar o aplicativo Skype for Business. Este tópico fala sobre telefones e versões de firmware que são compatíveis para uso no Skype for Business Online e apresenta outras informações que podem ajudar você quando estiver configurando telefones em sua organização.
  
Para obter as atualizações mais recentes e as informações atualizadas sobre os dispositivos compatíveis, confira o [Catálogo de dispositivos para Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
## <a name="supported-phones"></a>Telefones compatíveis

Para os usuários do Skype for Business Online, você pode escolher dentre vários modelos em  *Telefones certificados para o Skype for Business* e telefones que funcionam com Lync Phone Edition (LPE) listados na categoria do Skype for Business Online no [Catálogo de dispositivos do Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
A Microsoft está se associando e trabalhando em conjunto com Polycom, Yealink e AudioCodes para desenvolver e certificar uma ampla variedade de dispositivos por meio do Partner IP Phone Program (PIP) para o Sistema de Telefonia no Office 365 e no Skype for Business Server.
  
Ao fazer pedidos de novos telefones para o Skype for Business, é importante comprar telefones com o *ID de produtocorreto*. Esses ID's de produto garantirão que os telefones adquiridos já venham com a versão qualificada para o Skype for Business Online instalada.
  
|||
|:-----|:-----|
|**Parceiro de Telefone** <br/> |**ID do produto específico para o Skype for Business** <br/> |
|Polycom  <br/> |ID do Produto -019  <br/> |
|Yealink  <br/> |SIP-TXXG Skype for Business Edition  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Para obter mais detalhes sobre os telefones Polycom, veja [Soluções de voz para Microsoft](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
  
Para obter mais detalhes sobre os telefones Yealink, veja [Telefones IP do Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Para obter mais detalhes sobre os telefones AudioCodes, veja [Telefones IP para Skype for Business](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> O Lync Phone Edition é compatível com o Skype for Business Online, mas não com o Microsoft Teams. O suporte base para a plataforma LPE terminou em 10 de abril de 2014, e o suporte estendido vai até 11 de abril de 2023 a fim de alinhá-lo com o ciclo de vida do suporte do produto Lync Server 2013. Veja [Ciclo de vida de produtos Microsoft](https://support.microsoft.com/en-us/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) para obter detalhes sobre o ciclo de vida do LPE. Os modelos LPE CAP não são compatíveis com o Skype for Business Online.
>
> Este ano, o Office 365 não dará suporte a nenhuma versão do TLS anterior a 1.2. Como o sistema operacional subjacente do LPE não oferece suporte a TLS 1.2, LPE não poderá mais se conectar ao Office 365. Para obter mais informações, consulte o [Preparando para o uso obrigatório de TLS 1.2 no Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="supported-firmware"></a>Firmware compatível

Esta é a versão mínima de software necessária para telefones compatíveis trabalharem com o Sistema de Telefonia no Office 365:
  
||||
|:-----|:-----|:-----|
|**Tipo de telefone** <br/> |**Firmware mínimo** <br/> |**Data de lançamento** <br/> |
|Otimizado (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Maio 2015  <br/> |
|Série VVX Polycom Certificada  <br/> |5.4.0A  <br/> |Dezembro de 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Fevereiro de 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Dezembro de 2016  <br/> |
   
> [!NOTE]
[!OBSERVAçãO] Os telefones Lync Phone Edition (LPE) configurados para sua implantação local devem ser atualizados para o firmware mínimo ou superior necessário antes de você mover esses usuários para o Skype for Business Online. Se você mover os usuários locais para o Skype for Business Online antes de atualizar o firmware nos telefones, esses telefones não poderão conectar-se ao Skype for Business Online. 
  
## <a name="required-licenses"></a>Licenças necessárias

O Skype for Business Online não requer quaisquer licenças adicionais da Microsoft além das licenças do usuário. Para saber mais sobre as licenças de usuário necessárias, consulte [Licenciamento de complementos do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
O modelo de licenciamento do fabricante pode variar entre SIP aberto e firmware certificado para o Skype for Business. Se você estiver reorientando um modelo de certificado com um firmware de SIP aberto, deverá verificar os requisitos de licenciamento do firmware com o fabricante.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Conjunto de recursos dos telefones conectados ao Skype for Business Online

Para conhecer os recursos e capacidades completos do dispositivo, consulte os guias de usuário do fabricante.
  
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
|Upload de log  <br/> <br/> **Observação:** Atualmente, todo os logs são carregados somente para a equipe de Suporte da Microsoft, o acesso do cliente aos logs do telefone ainda não está disponível.           |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Autenticação moderna  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Vários Números de Emergência  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |Sim  <br/> |
|Integração com o calendário do Exchange*  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> <br/> **Observação:** Requer PC tethering           |
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

[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 