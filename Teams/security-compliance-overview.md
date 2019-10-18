---
title: Visão geral de segurança e conformidade no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Uma visão geral dos recursos de segurança e conformidade do Microsoft Teams, incluindo auditoria e relatórios, pesquisa de conteúdo de conformidade, descoberta eletrônica e muito mais.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: f5780720cfcd5adcf079c0f3d31423949cecea23
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568052"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Visão geral de segurança e conformidade no Microsoft Teams
======================================================

O Microsoft Teams está criado na nuvem empresarial de grande escala do Office 365, oferecendo os recursos avançados de segurança e conformidade que nossos clientes esperam.

O Teams é compatível com a camada D. Isso inclui as seguintes normas: ISO 27001, ISO 27018, SSAE16 SOC 1 e SOC 2, HIPAA e EU Model Clauses (EUMC). Dentro da estrutura de conformidade da Microsoft, a Microsoft classifica os aplicativos e serviços do Office 365 em quatro categorias. Cada categoria é definida por compromissos de conformidade específicos que devem ser atendidos por um serviço do Office 365 ou um serviço relacionado da Microsoft para que sejam listados naquela categoria.

Os serviços das categorias de conformidade C e D que têm compromissos de conformidade líderes do setor estão habilitados por padrão. Os serviços das categorias A e B vêm com controles de ativação ou desativação para a organização inteira. Você pode encontrar detalhes em [Estrutura de conformidade para as normas e regulamentos do setor](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf). O Microsoft Teams também dá suporte à conformidade com o Cloud Security Alliance.

O Teams também aplica uma autenticação de dois fatores para todas as equipe e organizações, registro único através do diretório ativo e criptografia de dados em trânsito e em repouso. Os arquivos ficam armazenados no SharePoint e são respaldados pela criptografia do SharePoint. As notas ficam armazenadas no OneNote e são respaldadas pela criptografia do OneNote. Os dados do OneNote são armazenados no site de equipe do SharePoint. A guia wiki também pode ser usada para fazer anotações, e o conteúdo dele também é armazenado no site de equipe do SharePoint.

Também acrescentamos suporte para pesquisa de registros de auditoria, eDiscovery e retenção legal para canais, bate-papos e arquivos, bem como gerenciamento de aplicativos móveis com o Microsoft Intune. Vá para o centro de conformidade & segurança do Office 365 para gerenciar essas configurações. 

Para saber mais sobre a conformidade com & de segurança do Office 365, leia [configurar seu locatário do office 365 para aumentar a segurança](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)

## <a name="auditing-and-reporting"></a>Auditoria e relatórios

A pesquisa de log de auditoria se conecta diretamente ao centro de conformidade do Office 365 Security & e expõe habilidades para definir alertas e/ou relatar eventos de auditoria, disponibilizando a exportação da carga de trabalho específica ou de conjuntos de eventos genéricos para uso e investigação de administração, em um linha do tempo de auditoria ilimitada. Todos os dados de log de auditoria estão disponíveis para configurar alertas no centro de conformidade & segurança do Office 365, bem como para filtragem e exportação para análise adicional. Consulte este [link](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) para saber mais sobre como realizar uma pesquisa de log de auditoria para eventos do Microsoft Teams no centro de conformidade do Office 365 Security &. 

## <a name="compliance-content-search"></a>Pesquisa de conteúdo de conformidade

A pesquisa de conteúdo pode ser usada para pesquisar todos os dados do teams por meio de recursos sofisticados de filtragem e exportados para um contêiner específico de conformidade e suporte jurídico. Isso pode ser feito com ou sem um caso do eDiscovery. Isso permite que os administradores de conformidade coletem dados do teams em todos os usuários, analise e exporte-os para processamento adicional. Consulte este [link](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) para saber mais sobre como conduzir um conteúdo de pesquisa de conteúdo de conformidade para o conteúdo do Microsoft Teams no centro de conformidade do Office 365 Security &. 

Dica: o tipo Microsoft Teams pode ser usado para filtrar somente o conteúdo do Microsoft Teams, ou seja, mensagens de chat e de canal, reuniões e chamadas. 

## <a name="ediscovery"></a>eDiscovery

A descoberta eletrônica é o aspecto eletrônico de identificar, coletar e produzir informações armazenadas eletronicamente (ESI) em resposta a uma solicitação de produção em uma ação judicial ou investigação. Recursos incluem gerenciamento de casos, preservação, pesquisa, análise e exportação de dados do teams. Isso inclui chats, mensagens e arquivos, reuniões e resumos de chamadas. Para reuniões e chamadas do Teams, um resumo dos eventos que aconteceram na reunião e na chamada são criados e disponibilizados na descoberta eletrônica. 

Para obter mais detalhes sobre como fazer a descoberta eletrônica em segurança & centro de conformidade e executar pesquisa de conteúdo de conformidade para conteúdo de equipes, acesse os links abaixo: 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[Pesquisa de conteúdo](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

Os clientes podem aproveitar a descoberta eletrônica in-loco ou [descoberta eletrônica avançada] por seushttps://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)requisitos (. As diferenças entre os dois estão destacadas na tabela a seguir:


| |In-place eDiscovery  |Advanced eDiscovery  |
|---------|---------|---------|
|Gestão de casos     |X        |X         |
|Controle de acesso  |X         |X         |
|Pesquisa de conteúdo     |X         | X        |
|Retenções   |X         | X        |
|Exportar     |X         |X         |
|Detecção de duplicidade     |-         |X         |
|Pesquisa de relevância com aprendizagem de máquina    |-         |X         |
|Análise de dados não estruturados      |-         |X         |


## <a name="legal-hold"></a>Retenção legal

Durante um litígio, muitas vezes é necessário que todos os dados associados a um usuário (responsáveis) ou uma equipe sejam preservados imutavelmente para que possam ser usados como evidências para o caso. Isso é conseguido colocando um usuário (caixa de correio do usuário) ou uma equipe em retenção legal. Quando qualquer equipe do teams é colocada no bloqueio in-loco (subconjunto da caixa de correio ou conjunto de sites por meio de consultas direcionadas ou conteúdo filtrado) ou retenção de litígio (caixa de correio ou conjunto de sites inteiro), a retenção é colocada na caixa de correio de grupos. Isso garante que, mesmo se os usuários finais excluirem ou editarem mensagens de canal que estejam ingeridas na caixa de correio de grupo, cópias imutáveis desse conteúdo serão mantidas e estarão disponíveis na pesquisa de descoberta eletrônica. As retenções locais costumam ser aplicadas no contexto de um caso do eDiscovery. Consulte [este](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) artigo de ajuda para saber mais sobre preservação e suspensões no centro de conformidade do Office 365 Security &. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Arquitetura de proteção de informações do Microsoft Teams. 

A figura a seguir indica o fluxo de inclusão de dados do teams para os arquivos e as mensagens do Exchange e do SharePoint para Teams. 

![Diagrama do fluxo de trabalho de dados do teams ao Exchange e ao SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

A figura a seguir indica o fluxo de inclusão de reuniões e dados de chamadas do teams para o Exchange.

![Diagrama do fluxo de trabalho de reuniões e dados de chamadas do teams para o Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Pode haver um atraso de 24 horas para descobrir o conteúdo das equipes.

<a name="licensing"></a>Licenças
---------------

Quando falamos em recursos de proteção de informações, as assinaturas do Office 365 e as licenças autônomas associadas determinarão o conjunto de recursos disponíveis.


| Recurso de proteção da informação | Office 365 Business Essentials | Office 365 Business Premium | Office 365 Enterprise E1 | Office 365 Enterprise E3/E4 | Office 365 Enterprise E5 |
|-----------------------------------|--------------------------------|-----------------------------|--------------------------|-----------------------------|--------------------------|
|              Arquivamento              |               -                |              -              |            -             |             Sim             |           Sim            |
|        In-Place eDiscovery        |               -                |              -              |            -             |             Sim             |           Sim            |
|        Advanced eDiscovery        |               -                |              -              |            -             |              -              |           Sim            |
|            Retenção legal             |               -                |              -              |            -             |             Sim             |           Sim            |
|     Pesquisa de conteúdo de conformidade     |               -                |             Sim             |           Sim            |             Sim             |           Sim            |
|      Auditoria e relatórios       |              Sim               |             Sim             |           Sim            |             Sim             |           Sim            |
|       Acesso condicional\*        |              Sim               |             Sim             |           Sim            |             Sim             |           Sim            |

> [!NOTE]
> \*O acesso condicional precisa de licenças adicionais


| |  |  |
|---------|---------|---------|
|![Um ícone representando um ponto de decisão](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Ponto de decisão         |A sua organização tem as licenças necessárias para atender aos requisitos empresariais de conformidade e segurança?         |
|![Um ícone que representa as próximas etapas](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Próximas etapas         |Examine o licenciamento atual da sua organização e confirme se ela atende a todos os requisitos comerciais de conformidade e segurança.         |

Antes de habilitar qualquer um desses recursos, certifique-se de ter acesso ao centro de conformidade do & de segurança no centro de administração do Microsoft 365. Por padrão, os administradores de locatários têm acesso.

A pesquisa de conteúdo e a descoberta eletrônica não exigem capacitação no centro de conformidade do & de segurança.

<a name="location-of-data-in-teams"></a>Localização dos dados no Microsoft Teams
-------------------------

Os dados no Microsoft Teams residem na região geográfica associada ao seu locatário do Office 365. Atualmente, o Teams é compatível com a Austrália, Canadá, França, Índia, Japão, Reino Unido, Coréia do Sul, África do Sul, Américas, Ásia e África do Sul. 

> [!IMPORTANT]
> Atualmente, o Microsoft Teams oferece residências de dados na Austrália, no Canadá, na Índia, no Japão, no Reino Unido, na Coréia do Sul e na África do Sul para novos locatários. Um novo locatário é definido como aquele que não teve nenhum usuário sequer entrando no Microsoft Teams. Os locatários existentes da Austrália, Índia, Japão e Coréia do Sul continuarão a ter seus dados de equipe armazenados na região da Ásia. Os locatários existentes no Canadá continuarão a ter seus dados armazenados nas Américas. Locatários existentes na França, no Reino Unido e na África do Sul continuarão a ter seus dados armazenados na região da EMEA.

Mais informações sobre o centro de dados da África do Sul para Teams podem ser encontradas na postagem de blog do Varun Sagar, [o Microsoft Teams inicia a residência de dados do Sul Africana](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611).

Mais leituras sobre a residência de dados do Sul do Sul para o Teams vêm cortesia da postagem de blog do Varun Sagar, [o Microsoft Teams inicia a residência de dados do Sul](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171).

Para saber mais sobre o lançamento da residência de dados do Microsoft Teams da Índia e do Reino Unido, leia a postagem de Ansuman Acharya no blog, [Microsoft Teams launches India Data Residency, other geos coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827). 

Para obter mais informações sobre a residência de dados do Canadá para Teams, leia a postagem de blog do Varun Sagar, [o Microsoft Teams lança a residência de dados do Canadá, Austrália e Japão em breve](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Para saber mais sobre o lançamento da Austrália e do Japão Data Residency for Teams, leia a postagem de blog do Varun Sagar, [o Microsoft Teams inicia a residência de dados da Austrália e do Japão](https://go.microsoft.com/fwlink/?linkid=867773). 

Para saber mais sobre o lançamento da França data Residency for Teams, leia a postagem de blog do Varun Sagar, [o Microsoft Teams inicia a residência de dados da França](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466).

Para ver quais regiões alojam os dados do seu locatário, vá para o**perfil da organização**de**configurações** > do [Centro](https://portal.office.com/adminportal/home) > de administração do Microsoft 365. Role para baixo até **Local dos dados**. 

![Captura de tela da tabela de localização de dados, incluindo equipes no centro de administração](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>Como as políticas de acesso condicional funcionam para o Teams?
-------------------------

O Microsoft Teams depende muito do Exchange Online, do SharePoint Online e do Skype for Business online para cenários de produtividade básica, como reuniões, calendários, chats de interoperabilidade e compartilhamento de arquivos. As políticas de acesso condicional que são definidas para esses aplicativos de nuvem se aplicam ao Microsoft Teams quando um usuário entra diretamente no Microsoft Teams, em qualquer cliente. 

O Microsoft Teams é compatível separadamente como um aplicativo na nuvem nas políticas de acesso condicional do Azure Active Directory. As políticas de acesso condicional definidas para o aplicativo Cloud do Microsoft Teams se aplicam ao Microsoft Teams quando um usuário entra. No entanto, sem as políticas corretas em outros aplicativos, como o Exchange Online e o SharePoint Online, os usuários ainda poderão acessar esses recursos diretamente. Para obter mais informações sobre como configurar uma política de acesso condicional no portal do Azure, acesse: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Os clientes de desktop do Microsoft Teams para Windows e Mac dão suporte à autenticação moderna. A autenticação moderna traz a entrada com base na biblioteca de autenticação do Azure Active Directory (ADAL) para aplicativos cliente do Microsoft Office entre plataformas.

Aplicativo da área de trabalho do Microsoft Teams compatível com AppLocker.  Para obter mais informações sobre os pré-requisitos do AppLocker, consulte: requisitos para usar AppLockerhttps://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)(.

<a name="privacy-in-teams"></a>Privacidade no Microsoft Teams
--------------------------

Como cliente do Office 365, você detém e controla seus dados. A Microsoft não usa seus dados para nenhum outro fim, além de lhe fornecer o serviço ao qual você se inscreveu. Como um provedor de serviços, não examinamos seu e-mail, seus documentos nem suas equipes para publicidade ou propósitos que não estejam relacionados ao serviço. A Microsoft não tem acesso para carregar conteúdo. Assim como o OneDrive for Business e o SharePoint Online, os dados do cliente permanecem no locatário.

Confira mais informações sobre as informações relacionadas à segurança e confiança na [central de confiabilidade da Microsoft](https://microsoft.com/trustcenter). O Teams segue as mesmas diretrizes e princípios da central de confiabilidade da Microsoft.

<a name="related-topics"></a>Tópicos relacionados
----------------------
[Links confiáveis do Office 365 ATP](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)
