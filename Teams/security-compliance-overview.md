---
title: Visão geral de segurança e conformidade no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Uma visão geral dos recursos de segurança e conformidade do Microsoft Teams, incluindo auditoria e relatórios, pesquisa de conteúdo de conformidade, descoberta eletrônica e muito mais.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b687d528f7cb593039fdafd9dcc6ec08ec66372
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341639"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Segurança e conformidade no Microsoft Teams

> [!IMPORTANT]
> Como cliente do Office 365, você detém e controla seus dados. A Microsoft não usa seus dados para nenhum outro fim, além de lhe fornecer o serviço ao qual você se inscreveu. Como um provedor de serviços, não examinamos seu e-mail, seus documentos nem suas equipes para publicidade ou propósitos que não estejam relacionados ao serviço. A Microsoft não tem acesso para carregar conteúdo. Assim como o OneDrive for Business e o SharePoint Online, os dados do cliente permanecem no locatário. Você pode conferir mais informações sobre as informações relacionadas à segurança e confiança na [central de confiabilidade da Microsoft](https://microsoft.com/trustcenter). O Teams segue as mesmas diretrizes e princípios da central de confiabilidade da Microsoft.

O Microsoft Teams está criado na nuvem empresarial de grande escala do Office 365, oferecendo os recursos avançados de segurança e conformidade que nossos clientes esperam. Para obter mais informações sobre como planejar a segurança no O365, consulte o nosso conteúdo do O365. [O mapa de segurança do O365](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) é um bom lugar para começar. Para obter mais informações sobre como planejar a conformidade no O365, você pode começar com [o artigo planejar a segurança e conformidade](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance) .

Este artigo fornece mais informações sobre a segurança e a conformidade específicas ao Teams. Você deve revisar estes vídeos de mecânica da Microsoft sobre segurança e conformidade:

- [Fundamentos do Microsoft Teams para ti: segurança e conformidade](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Controles do Microsoft Teams para segurança e conformidade](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

## <a name="security"></a>Segurança

O Teams impõe a autenticação de dois fatores para toda a equipe e toda a organização, o logon único pelo Active Directory e a criptografia de dados em trânsito e em repouso. Os arquivos ficam armazenados no SharePoint e são respaldados pela criptografia do SharePoint. As notas ficam armazenadas no OneNote e são respaldadas pela criptografia do OneNote. Os dados do OneNote são armazenados no site de equipe do SharePoint. A guia wiki também pode ser usada para anotações e seu conteúdo também é armazenado no site de equipe do SharePoint.

Leia [modelos de identidade e autenticação](identify-models-authentication.md) para obter mais informações sobre autenticação e equipes e [como a autenticação moderna funcionará](sign-in-teams.md) com a autenticação moderna em particular.

Como as equipes trabalham em parceria com o SharePoint, o OneNote, o Exchange e muito mais, você deve se sentir confortável ao gerenciar a segurança no O365. Para saber mais sobre a segurança do Office 365, leia [configurar seu locatário do office 365 para aumentar a segurança](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> Atualmente, os [canais privados](private-channels.md) dão suporte a recursos limitados de segurança e conformidade. O suporte para todo o conjunto de recursos de segurança e conformidade em canais privados estará disponível em breve.

### <a name="advance-threat-protection-atp"></a>Proteção avançada contra ameaças (ATP)

A proteção avançada contra ameaças (ATP) está disponível para o Microsoft Teams, juntamente com o SharePoint e o OneDrive for Business, aplicativos que se integram ao Teams para gerenciamento de conteúdo. A ATP permite que você determine se o conteúdo desses aplicativos é de natureza maliciosa e bloqueia esse conteúdo do acesso do usuário.

Como o conteúdo afetado é gerenciado após a detecção há até as configurações que você selecionou no O365. É altamente recomendável que você considere todos os aplicativos quando a configuração ATP e para leitura adicional, o artigo do [Office 365 ATP para SharePoint, o onedrive e o Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) terá informações detalhadas sobre como começar.

### <a name="safe-links"></a>Links seguros

Enquanto isso, no momento, os links seguros de ATP não estão disponíveis no Microsoft Teams, agora eles estão em visualização pública por meio do programa de adoção de tecnologia (toque) e, enquanto uma data de lançamento para disponibilidade geral não está definida, atualizaremos este artigo quando chegarmos. Enquanto isso, para obter informações sobre links seguros do O365, confira os [links de segurança da ATP do Office 365](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection).

### <a name="how-conditional-access-policies-work-for-teams"></a>Como as políticas de acesso condicional funcionam para o Teams

O Microsoft Teams depende muito do Exchange Online, do SharePoint Online e do Skype for Business online para cenários de produtividade básica, como reuniões, calendários, chats de interoperabilidade e compartilhamento de arquivos. As políticas de acesso condicional que são definidas para esses aplicativos de nuvem se aplicam ao Microsoft Teams quando um usuário entra diretamente no Microsoft Teams, em qualquer cliente.

O Microsoft Teams é compatível separadamente como um aplicativo na nuvem nas políticas de acesso condicional do Azure Active Directory. As políticas de acesso condicional definidas para o aplicativo Cloud do Microsoft Teams se aplicam ao Microsoft Teams quando um usuário entra. No entanto, sem as políticas corretas em outros aplicativos, como o Exchange Online e o SharePoint Online, os usuários ainda poderão acessar esses recursos diretamente. Para obter mais informações sobre como configurar uma política de acesso condicional no portal do Azure, acesse: [início rápido do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

Os clientes de desktop do Microsoft Teams para Windows e Mac dão suporte à autenticação moderna. A autenticação moderna traz a entrada com base na biblioteca de autenticação do Azure Active Directory (ADAL) para aplicativos cliente do Microsoft Office entre plataformas.

Aplicativo da área de trabalho do Microsoft Teams compatível com AppLocker.  Para obter mais informações sobre os pré-requisitos do AppLocker, consulte: requisitos para usar o [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Conformidade

O Teams tem uma ampla gama de informações para ajudá-lo com áreas de conformidade, incluindo políticas de retenção, proteção contra perda de dados (DLP), descoberta eletrônica e retenção legal para canais, chats e arquivos, pesquisa de log de auditoria, bem como gerenciamento de aplicativos móveis com o Microsoft Intune. Fornecemos algumas informações sobre todos esses tópicos abaixo, e você pode ir para o centro de conformidade do Office 365 Security & para gerenciar essas configurações.

### <a name="retention-policies"></a>Políticas de retenção

As políticas de retenção no Microsoft Teams permitem manter os dados importantes para sua organização manter, para fins regulatórios, legais, de negócios ou outros motivos e também para remover conteúdo e comunicações que não sejam relevantes para serem retidos. Você também pode usar as políticas de retenção para manter os dados por um período de tempo e, em seguida, excluí-los. Para obter mais informações, consulte o artigo sobre as [políticas de retenção no Microsoft Teams](retention-policies.md) .

### <a name="data-loss-prevention-dlp"></a>Prevenção contra perda de dados (DLP)

A prevenção contra perda de dados (DLP) no Microsoft Teams, bem como a história de DLP maior para o O365, gira em torno da preparação para empresas quando se trata de proteger documentos confidenciais e dados no O365. Se você tiver dúvidas quanto às informações confidenciais em mensagens ou documentos, as políticas DLP poderão ajudar a garantir que os usuários não compartilhem esses dados confidenciais com as pessoas erradas.

Para obter informações sobre a prevenção contra perda de dados no Teams, consulte [DLP para Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams). Um bom artigo para preocupações com o O36 [https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)DLP é.

### <a name="ediscovery"></a>eDiscovery

Descoberta eletrônica, ou descoberta eletrônica, é o aspecto eletrônico de identificar, coletar e produzir informações armazenadas eletronicamente (ESI) em resposta a uma solicitação de produção em um naipe ou uma investigação legal. Recursos incluem gerenciamento de casos, preservação, pesquisa, análise e exportação de dados do teams. Isso inclui chats, mensagens e arquivos, reuniões e resumos de chamadas. Para reuniões e chamadas do Teams, um resumo dos eventos que aconteceram na reunião e na chamada são criados e disponibilizados na descoberta eletrônica.

Para obter mais detalhes sobre como fazer a descoberta eletrônica do O365 em segurança & centro de conformidade e executar pesquisa de conteúdo de conformidade para conteúdo de equipes, acesse os links abaixo:

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[Pesquisa de conteúdo](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Temos um artigo específico do teams para obter mais informações, [descoberta eletrônica de chats convidados a convidados](eDiscovery-investigation.md).

Os clientes podem aproveitar a descoberta eletrônica in-loco ou [descoberta eletrônica avançada] de acordo com suas [necessidades](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery). As diferenças entre os dois estão destacadas na tabela a seguir:

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

### <a name="legal-hold"></a>Retenção legal

Durante litígio, talvez você precise que todos os dados associados a um usuário (responsáveis) ou a uma equipe sejam preservados como imutáveis, para que possam ser usados como evidências para o caso. Isso pode ser feito colocando um usuário (caixa de correio do usuário) ou uma equipe em retenção legal. Para um controle legal da equipe, a caixa de correio da equipe pode ser colocada nas seguintes isenções:

- Bloqueio in-loco (um subconjunto da caixa de correio ou conjunto de sites por meio de consultas direcionadas ou conteúdo filtrado é colocado em espera) ou
- Retenção de litígio (a caixa de correio ou o conjunto de sites inteiro é colocado em espera).

Em ambos os casos, quando a retenção é definida, isso garante que, mesmo se os usuários finais excluirem ou editarem mensagens de canal na caixa de correio de grupo, cópias imutáveis desse conteúdo serão mantidas e estarão disponíveis por meio de pesquisa de descoberta eletrônica. Controles legais geralmente são aplicados dentro do contexto de um caso de descoberta eletrônica.

Consulte o artigo [visão geral do artigo sobre as políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) para saber mais sobre preservação e suspensões no centro de conformidade do Office 365 Security &. Para saber mais sobre as informações específicas do teams em controle legal, também temos [o artigo colocar um usuário ou equipe do Microsoft Teams em um artigo de controle legal](legal-hold.md) para obter mais informações.

### <a name="compliance-content-search"></a>Pesquisa de conteúdo de conformidade

A pesquisa de conteúdo pode ser usada para pesquisar todos os dados do teams por meio de recursos avançados de filtragem. Os dados resultantes podem ser exportados para um contêiner específico para suporte à conformidade e litígio. Isso pode ser feito com ou sem um caso do eDiscovery. Isso permite que os administradores de conformidade coletem dados do teams em todos os usuários, analise e exporte-os para processamento adicional. Consulte este artigo [Pesquisar conteúdo no O365](https://docs.microsoft.com/microsoft-365/compliance/content-search) para saber mais sobre como conduzir uma pesquisa de conteúdo de conformidade para o Microsoft Teams e outros conteúdos do O365 no centro de conformidade do Office 365 Security &.

> [!TIP]
> Usando a pesquisa de conteúdo, você pode filtrar somente conteúdo do Microsoft Teams, como mensagens de chat e de canal, reuniões e chamadas, se necessário.

Se quiser informações específicas de outras equipes sobre como configurar a pesquisa de conteúdo, examine o artigo [Pesquisar conteúdo no Microsoft Teams](content-search.md) .

### <a name="auditing-and-reporting"></a>Auditoria e relatórios

A pesquisa de log de auditoria se conecta diretamente ao centro de conformidade do Office 365 Security & e oferece a capacidade de definir alertas, bem como relatar eventos de auditoria, permitindo a exportação de conjuntos de eventos genéricos ou de carga de trabalho para uso e investigação de administração em uma linha do tempo de auditoria ilimitada. Você pode configurar alertas para todos os dados de log de auditoria no centro de conformidade do Office 365 Security & e filtrar e exportar esses dados para análise adicional. Consulte o artigo [Pesquisar o log de auditoria](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) para saber mais sobre como conduzir um log de auditoria para o O365. Para saber mais sobre como Pesquisar eventos do Microsoft Teams no centro de conformidade do Office 365 Security &, também temos o artigo [ativar a auditoria no artigo do teams](audit-log-events.md) para revisão.

## <a name="information-protection-architecture"></a>Arquitetura de proteção de informações

A figura a seguir indica o fluxo de inclusão de dados do teams para os arquivos e as mensagens do Exchange e do SharePoint para Teams.

![Diagrama do fluxo de trabalho de dados do teams ao Exchange e ao SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

A figura a seguir indica o fluxo de inclusão de reuniões e dados de chamadas do teams para o Exchange.

![Diagrama do fluxo de trabalho de reuniões e dados de chamadas do teams para o Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Pode haver um atraso de 24 horas para descobrir o conteúdo das equipes.

## <a name="licensing"></a>Licenças

Quando se trata de recursos de proteção de informações, as assinaturas do Office 365 e as licenças autônomas associadas determinarão o conjunto de recursos disponíveis.

Para obter informações sobre como determinar o licenciamento precisa implementar recursos de segurança e conformidade, consulte: [Licenciamento para o Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

> [!NOTE]
> A pesquisa de conteúdo e a descoberta eletrônica não precisam ser habilitadas no centro de conformidade do & de segurança para funcionar.

## <a name="location-of-data-in-teams"></a>Localização dos dados no Microsoft Teams

Os dados no Microsoft Teams residem na região geográfica associada ao seu locatário do Office 365. Para ver em quais regiões há suporte no momento, examine a [localização dos dados no Microsoft Teams](location-of-data-in-teams.md).

Se você precisar ver qual região abriga os dados para o seu locatário, vá para o**perfil da organização**de**configurações** > do [Centro](https://portal.office.com/adminportal/home) > de administração do Microsoft 365. Role para baixo até **Local dos dados**.

![Captura de tela da tabela de localização de dados, incluindo equipes no centro de administração](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Padrões de conformidade

O Teams é compatível com a camada D. Isso inclui as seguintes normas: ISO 27001, ISO 27018, SSAE16 SOC 1 e SOC 2, HIPAA e EU Model Clauses (EUMC). Dentro da estrutura de conformidade da Microsoft, a Microsoft classifica os aplicativos e serviços do Office 365 em quatro categorias. Cada categoria é definida por compromissos de conformidade específicos que devem ser atendidos por um serviço do Office 365 ou um serviço relacionado da Microsoft para que sejam listados naquela categoria.

Os serviços das categorias de conformidade C e D que têm compromissos de conformidade líderes do setor estão habilitados por padrão. Os serviços das categorias A e B vêm com controles de ativação ou desativação para a organização inteira. Você pode encontrar detalhes em [Estrutura de conformidade para as normas e regulamentos do setor](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf). O Microsoft Teams também dá suporte à conformidade com o Cloud Security Alliance.

## <a name="related-topics"></a>Tópicos relacionados

[M365 Security](https://docs.microsoft.com/microsoft-365/security/)
[M365 Compliance](https://docs.microsoft.com/microsoft-365/compliance/)
