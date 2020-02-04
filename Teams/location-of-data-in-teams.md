---
title: Localização de dados no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: Saiba mais sobre onde os dados são armazenados no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24432b0854ac0c4256f5d097bacfca5f1a392d72
ms.sourcegitcommit: 2cb46af39a0d116e8fd020aa04bd2ecbd6998a5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41679047"
---
# <a name="location-of-data-in-microsoft-teams"></a>Localização de dados no Microsoft Teams

Os dados no Microsoft Teams residem na região geográfica associada ao seu locatário do Office 365. Atualmente, o Teams é compatível com a Austrália, Canadá, França, Alemanha, Índia, Japão, África do Sul, Coréia do Sul, Suíça (que inclui o Liechtenstein), os Emirados Árabes Unidos, Reino Unido, Américas, Ásia-Pacífico e territórios da EMEA. 

> [!IMPORTANT]
> Atualmente, o Teams oferece residências de dados na Austrália, no Canadá, na França, na Índia, no Japão, nos Emirados Árabes Unidos, no Reino Unido, na Coréia do Sul, na África do Sul e na Suíça (que inclui o Liechtenstein) apenas para novos locatários.
> Um novo locatário é definido como aquele que não teve nenhum usuário sequer entrando no Microsoft Teams. Os locatários existentes da Austrália, Índia, Japão e Coréia do Sul continuarão a ter seus dados de equipe armazenados na região da Ásia. Os locatários existentes no Canadá continuarão a ter seus dados armazenados nas Américas. Locatários existentes na França, na Alemanha, no Liechtenstein, nos Emirados Árabes Unidos, no Reino Unido, na África do Sul e na Suíça terão seus dados armazenados na região da EMEA.

## <a name="where-your-teams-data-is-stored"></a>Onde os dados de suas equipes são armazenados

Para ver quais regiões alojam os dados do seu locatário, vá para o**perfil da organização**de**configurações** > do [Centro](https://portal.office.com/adminportal/home) > de administração do Microsoft 365. Role para baixo até **Local dos dados**.

![Captura de tela da tabela de localização de dados, incluindo equipes no centro de administração](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Localização de dados do teams em repouso

Seus dados de equipe são armazenados de forma diferente dependendo do tipo de conteúdo. 

![Diagrama mostrando tipos de conteúdo de equipes e onde eles são armazenados em repouso](media/location-of-data-storage-at-rest.png)

Confira a [sessão de debates do Ignite na arquitetura do Microsoft Teams](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) para uma discussão aprofundada.

### <a name="core-teams-customer-data"></a>Dados principais do cliente das equipes

Se o seu locatário estiver provisionado na Austrália, no Canadá, na União Européia, na França, na Alemanha, na Índia, no Japão, na África do Sul, na Coréia do Sul (que inclui o Liechtenstein), os Emirados Árabes Unidos, o Reino Unido ou os Estados Unidos, a Microsoft armazena os dados do cliente a seguir em repouso somente nesse local:

- Chats de equipe, conversas de canal e de equipe, imagens, mensagens de correio de voz e contatos
- Conteúdo do site do SharePoint Online e os arquivos armazenados nesse site
- Arquivos carregados no OneDrive for Business

#### <a name="chat-channel-messages-team-structure"></a>Chat, mensagens de canal, estrutura da equipe

Todas as equipes do teams são apoiadas por um grupo do Office 365 e seu site do SharePoint e caixa de correio do Exchange. Chats privados (incluindo chats em grupo), mensagens enviadas como parte de uma conversa em um canal, e a estrutura de equipes e canais são armazenadas em um serviço de chat em execução no Azure. Os dados também são armazenados em uma pasta oculta nas caixas de correio de usuários e grupos para habilitar os recursos de proteção de informações.

#### <a name="voicemail-and-contacts"></a>Correio de voz e contatos

Os correios de voz são armazenados no Exchange. Os contatos são armazenados no armazenamento de dados na nuvem baseado no Exchange. O Exchange e o armazenamento em nuvem baseado no Exchange já fornecem residência de dados em cada um dos GEOS mundiais do datacenter. Para todas as equipes, correios de voz e contatos são armazenados no país da Austrália, Canadá, França, Alemanha, Índia, Alemanha, Reino Unido, Reino Unido, África do Sul, Coréia do Sul, Suíça (inclui o Liechtenstein) e Estados Unidos. Para todos os outros países, os arquivos são armazenados nos locais EUA, Europa ou Ásia Pacífico com base na afinidade de locatários.

#### <a name="images-and-media"></a>Imagens e mídia

Mídia usada em chats (exceto GIFs Giphy que não são armazenados, mas são um link de referência para a URL do serviço original do Giphy, o Giphy é um serviço que não é da Microsoft) é armazenado em um serviço de mídia baseado no Azure que é implantado nos mesmos locais do serviço de chat.

#### <a name="files"></a>Arquivos

Arquivos (incluindo o OneNote e o wiki) que alguém compartilha em um canal são armazenados no site do SharePoint da equipe. Arquivos compartilhados em um chat particular ou chat durante uma reunião ou chamada são carregados e armazenados no OneDrive para a conta empresarial do usuário que compartilha o arquivo. O Exchange, o SharePoint e o OneDrive já fornecem residência de dados em cada um dos GEOS mundiais do datacenter. Portanto, para clientes existentes, todos os arquivos, blocos de anotações do OneNote, conteúdo wiki do Teams e caixas de correio que fazem parte da experiência do teams já estão armazenados no local com base na afinidade do locatário. Os arquivos são armazenados no país para a Austrália, Canadá, França, Alemanha, Alemanha, Reino Unido, Emirados Árabes Unidos, Reino Unido, África do Sul, Coréia do Sul e Suíça (que inclui o Liechtenstein). Para todos os outros países, os arquivos são armazenados nos locais EUA, Europa ou Pacífico asiático com base na afinidade de locatários.

### <a name="datacenter-locations"></a>Locais do datacenter

Os serviços do teams descritos nesta seção armazenam dados em repouso nos seguintes locais:

|País ou região  |Localização do Data Center |
|---------|---------|
|Austrália   |Novo Sul Gales e Victoria         |
|Canadá    |Cidade de Quebec e Toronto         |
|França    |Marseille e Paris         |
|Alemanha    |Berlim e Frankfurt      |
|Índia   |Chennai e pune        |
|Japão    |Tóquio (Saitama) e Osaka         |
|Liechtenstein   |Geneva e Zurique       |
|África do Sul     |Cidade Joanesburgo e cabo         |
|Coreia do Sul     |Seul e Busan         |
|Suíça    |Geneva e Zurique       |
|Emirados Árabes Unidos     |Abu Dhabi e Dubai         |
|Reino Unido     | Cardiff e Londres        |
|Américas – norte e Sul (AMER) |Bay, CA e Boydton, VA       |
|Pacífico Asiático (Ásia)  |Cingapura e Hong Kong        |
|Europa, Oriente Médio e Ásia (EMEA)   |Dublin e Amsterdã        |

> [!NOTE]
> Para o Liechtenstein, os dados são armazenados em repouso nos data centers da Suíça em Geneva e Zurique.

### <a name="data-stored-with-a-third-party-storage-provider"></a>Dados armazenados com um provedor de armazenamento de terceiros

As organizações que permitem aos usuários armazenar arquivos com um provedor de armazenamento de terceiros dependem do local de armazenamento desses serviços e devem, portanto, analisar a localização dos dados em repouso para esses serviços separadamente.

- **Guias**: as guias permitem aos usuários fixar informações de aplicativos e serviços em um canal. Portanto, ele varia de acordo com o tipo da guia em que os dados são armazenados. A guia em si não armazena dados. Por exemplo, uma guia do SharePoint armazenará dados com base no local em que o conjunto de sites do SharePoint foi provisionado. Uma guia que inclui informações de um parceiro armazenará os dados diretamente no sistema usado pelo parceiro e só apresentará um modo de exibição.
- **Outros aplicativos de parceiros**: a Microsoft não fornece suporte de residência de dados para aplicativos e serviços de parceiros que você possa estar usando na experiência do teams. Revise as informações dessas soluções diretamente para saber onde seus dados estão sendo armazenados.

## <a name="see-also"></a>Confira também

- [O Microsoft Teams inicia a residência de dados dos Emirados Árabes Unidos](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [O Microsoft Teams inicia a residência de dados do sul coreano](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [O Microsoft Teams inicia a residência de dados do Sul Africana](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [O Microsoft Teams inicia a residência de dados da França](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [O Microsoft Teams inicia a residência de dados da Índia, outros GEOS em breve](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [O Microsoft Teams inicia a residência de dados da Austrália e do Japão](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [O Microsoft Teams lança a residência de dados do Canadá, Austrália e Japão em breve](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
