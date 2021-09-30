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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Saiba quais telefones da Polycom, HP, and Mitel funcionam com o Skype for Business e as licenças necessárias. '
ms.openlocfilehash: 4b4a5e48a531a694b006126221ddc7fcba40e1c3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013145"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obter telefones para o Skype for Business Online

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

Skype for Business Online qualifica e dá suporte a telefones de área de trabalho para usuários que querem ter uma experiência de telefone tradicional, em vez de usar o Skype for Business aplicativo. Este tópico aborda os telefones e versões de firmware com suporte para uso no Skype for Business Online e outras informações que podem ajudá-lo ao configurar telefones em sua organização.

> [!NOTE]
> Skype Para Empresas, lentamente será substituído pelo Microsoft Teams como o método de comunicação principal no Microsoft 365 e Office 365.  Consulte [Uma nova visão para comunicações inteligentes no Office 365](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/) para obter mais informações.
>
>Para obter as atualizações mais recentes e informações mais atualizadas sobre dispositivos com suporte, consulte o Microsoft Teams [para comunicações inteligentes.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)
  
## <a name="supported-phones"></a>Telefones compatíveis
  
A Microsoft está fazendo parcerias e trabalhando em estreita parceria com Polycom, Yealink e AudioCodes para desenvolver e certificar uma ampla variedade de dispositivos por meio do Programa de Telefone IP do parceiro (PIP) para o Sistema de Telefonia.
  
Ao solicitar novos telefones para Skype for Business, é importante comprar telefones com a *ID do produto correta.* Essas IDs de produto garantirão que os telefones recebidos tenham a versão Skype for Business online já instalada.
  
|Parceiro de Telefone  |ID do produto específico para o Skype for Business  |
|:-----|:-----|
|Polycom   |ID do Produto -019   |
|Yealink   |SIP-TXXG Skype for Business Edition   |
|AudioCodes   |UCXXXHDEG (SfB)   |
   
Para obter mais detalhes sobre telefones Polycom, consulte [Poly Documentation Library](https://documents.polycom.com/category/voice).
  
Para obter mais detalhes sobre os telefones Yealink, veja [Telefones IP do Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Para obter mais detalhes sobre telefones AudioCodes, [consulte Skype for Business IP Phones](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> O Lync Telefone Edition é suportado com Skype for Business Online, mas não com Microsoft Teams. O suporte principal para a plataforma LPE terminou em 10/10/2014, com suporte estendido até 11/11/2023 para se alinhar ao ciclo de vida do suporte ao produto do Lync Server 2013. Consulte [Ciclo de Vida do Produto](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) da Microsoft para obter detalhes sobre o ciclo de vida do LPE. Modelos de CAP LPE não são suportados com Skype for Business Online.
>
> Este ano, o Office 365 não dará suporte a nenhuma versão do TLS anterior a 1.2. Como o sistema operacional subjacente do LPE não oferece suporte a TLS 1.2, LPE não poderá mais se conectar ao Office 365. Para obter mais informações, consulte o [Preparando para o uso obrigatório de TLS 1.2 no Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="supported-firmware"></a>Firmware com suporte

Esta é a versão mínima de software necessária para que os telefones com suporte funcionem com Sistema de Telefonia:
  

|Tipo de telefone |Firmware mínimo |Data de lançamento |
|:-----|:-----|:-----|
|Otimizado (Lync Phone Edition)   |4.0.7577.4463   |Maio 2015   |
|Série VVX Polycom Certificada   |5.4.0A   |Dezembro de 2015   |
|Yealink   |X.8.1.52   |Fevereiro de 2017   |
|AudioCodes   |3.0.0.459.1   |Dezembro de 2016   |

Para obter mais detalhes sobre as versões de firmware certificados atuais, [consulte Skype for Business IP Phones](../../../SfbPartnerCertification/certification/devices-ip-phones.md).

> [!NOTE]
> [!OBSERVAçãO] Os telefones Lync Phone Edition (LPE) configurados para sua implantação local devem ser atualizados para o firmware mínimo ou superior necessário antes de você mover esses usuários para o Skype for Business Online. Se você mover os usuários locais para o Skype for Business Online antes de atualizar o firmware nos telefones, esses telefones não poderão conectar-se ao Skype for Business Online. 
  
## <a name="required-licenses"></a>Licenças necessárias

Skype for Business Online não exige nenhuma licença adicional da Microsoft além das licenças de usuário. Para saber mais sobre as licenças de usuário necessárias, consulte [Skype for Business e Microsoft Teams de complemento.](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
Os modelos de licenciamento do fabricante podem variar entre o SIP aberto e Skype for Business firmware certificado. Se você estiver reorientando um modelo de certificado com um firmware de SIP aberto, deverá verificar os requisitos de licenciamento do firmware com o fabricante.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype for Business Conjunto de recursos de telefones conectados online

Para recursos e recursos completos do dispositivo, verifique os guias de usuário do fabricante.
  

|Recurso  |Polycom 3PIP  |Yealink 3PIP |AudioCodes 3PIP |LPE |
|:-----|:-----|:-----|:-----|:-----|
|Entre com as credenciais dos usuários   |Sim  |Sim   |Sim   |Não   |
|Entrar via PC (Emparelhamento), somente Windows   |Sim   |Sim   |Sim   |Sim   |
|Entrar usando (Entrada na Web)  <br/>  <br/> **Observação:** Verifique a matriz de suporte no guia de implantação.  |Sim   |Sim   |Sim   |Não   |
|Clique único para ingressar na reunião   |Sim   |Sim   |Sim   |Sim   |
|Clique para discar (Emparelhamento)   |Sim   |Sim   |Sim   |Sim > |
|Controles de reunião   |Sim   |Sim   |Sim   |Sim   |
|Caixa postal visual   |Sim   |Sim   |Sim   |Sim   |
|Trava de telefone   |Sim   |Sim   |Sim   |Sim   |
|Atualização de dispositivo   |Sim   |Sim   |Sim   |Sim   |
|Provisionamento em banda   |Sim   |Sim   |Sim   |Sim   |
|QoE   |Sim   |Sim   |Sim   |Não  |
|Upload de log  <br/> <br/> **Observação:** Atualmente, todos os logs são carregados apenas para a equipe de Suporte da Microsoft; o acesso do cliente aos logs de telefone ainda não está disponível.           |Sim   |Sim   |Sim   |Sim   |
|Autenticação moderna   |Sim   |Sim   |Sim   |Não   |
|Vários Números de Emergência   |Sim   |Não   |Não   |Sim   |
|Integração com o calendário do Exchange*   |Sim   |Sim   |Sim   |Sim  <br/> <br/> **Observação:** Requer a adoção de um computador           |
|Integração de presença   |Sim   |Sim   |Sim   |Sim   |
|Diretório Corporativo   |Sim   |Sim   |Sim   |Sim   |
|Delegação   |Sim   |Sim   |Sim   |Não   |
|Integração da imagem do contato   |Não   |Sim  |Não   |Sim   |


     
> [!NOTE]
> CX 600 ou quaisquer outros telefones Aries não oferecem suporte a autenticação multifator (MFA). Se você forçar MFA, esses dispositivos não poderão se conectar. Esses dispositivos devem usar somente ID da organização para autenticação.
 
## <a name="what-else-should-you-know"></a>O que mais você deve saber?
Para obter instruções de configuração passo a passo, veja [Implantar telefones para o Skype for Business Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Tópicos relacionados
[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Veja o que você obtém com o Sistema de Telefonia](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
