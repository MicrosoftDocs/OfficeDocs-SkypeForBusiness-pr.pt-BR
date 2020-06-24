---
title: Visão geral da segurança e conformidade
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
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33c09a92d8c23d8bc4c13c9a131eb82733378840
ms.sourcegitcommit: 44e47c3b2eb44c38cb8d761befdc6c0cef7c61bc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2020
ms.locfileid: "44841892"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Segurança e conformidade no Microsoft Teams

> [!IMPORTANT]
> Para saber mais sobre como garantir a **segurança enquanto todos estiverem trabalhando em casa durante a epidemia do COVID-19**, leia estes artigos:
>  - [As 12 principais tarefas para as equipes de segurança dar suporte ao trabalho em casa](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Otimize a conectividade do Microsoft 365 ou do Office 365 para usuários remotos usando o tunelamento dividido da VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Atualizado em 2 de abril de 2020: [Guia de segurança do teams](teams-security-guide.md)


O Microsoft Teams foi criado com base no Microsoft 365 e no Office 365 Hyper-Scale, nuvem de nível empresarial, oferecendo os recursos avançados de segurança e conformidade que nossos clientes esperam. Para obter mais informações sobre como planejar a segurança no Microsoft 365 ou no Office 365, [o mapa de segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) é um bom lugar para começar. Para obter mais informações sobre como planejar a conformidade do Microsoft 365 ou do Office 365, você pode começar com [o artigo plano para segurança e conformidade](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance) .


Este artigo fornece mais informações sobre a segurança e a conformidade específicas ao Teams. Não perca esses vídeos de mecânica da Microsoft sobre segurança e conformidade:

- [Fundamentos do Microsoft Teams para ti: segurança e conformidade](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Controles do Microsoft Teams para segurança e conformidade](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> Como cliente do Microsoft 365 ou do Office 365, você tem e controla os seus dados. A Microsoft não usa seus dados para nenhum outro fim, além de lhe fornecer o serviço ao qual você se inscreveu. Como um provedor de serviços, não examinamos seu e-mail, seus documentos nem suas equipes para publicidade ou propósitos que não estejam relacionados ao serviço. A Microsoft não tem acesso ao conteúdo carregado. Assim como o OneDrive for Business e o SharePoint Online, os dados do cliente permanecem no locatário. Você pode conferir mais informações sobre as informações relacionadas à segurança e confiança na [central de confiabilidade da Microsoft](https://microsoft.com/trustcenter). O Teams segue as mesmas diretrizes e princípios da central de confiabilidade da Microsoft.

## <a name="security"></a>Segurança

O Teams impõe a autenticação de dois fatores para toda a equipe e toda a organização, o logon único pelo Active Directory e a criptografia de dados em trânsito e em repouso. Os arquivos ficam armazenados no SharePoint e são respaldados pela criptografia do SharePoint. As notas ficam armazenadas no OneNote e são respaldadas pela criptografia do OneNote. Os dados do OneNote são armazenados no site de equipe do SharePoint. A guia wiki também pode ser usada para anotações e seu conteúdo também é armazenado no site de equipe do SharePoint.

Leia [modelos de identidade e autenticação](identify-models-authentication.md) para obter mais informações sobre autenticação e equipes e [como a autenticação moderna funcionará](sign-in-teams.md) com a autenticação moderna em particular.

Como as equipes trabalham em parceria com o SharePoint, o OneNote, o Exchange e muito mais, você deve se sentir confortável ao gerenciar a segurança no Microsoft 365 ou no Office 365. Para saber mais, leia sobre[como configurar sua organização do Microsoft 365 ou do Office 365 para aumentar a segurança](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> Atualmente, os [canais privados](private-channels.md) dão suporte a recursos limitados de segurança e conformidade. O suporte para todo o conjunto de recursos de segurança e conformidade em canais privados estará disponível em breve.

### <a name="advanced-threat-protection-atp"></a>Proteção avançada contra ameaças (ATP)

A proteção avançada contra ameaças (ATP) está disponível para o Microsoft Teams, juntamente com o SharePoint e o OneDrive for Business, aplicativos que se integram ao Teams para gerenciamento de conteúdo. A ATP permite que você determine se o conteúdo desses aplicativos é de natureza maliciosa e bloqueia esse conteúdo do acesso do usuário.

Como o conteúdo afetado é gerenciado após a detecção, há até as configurações que você selecionou no Microsoft 365 ou no Office 365. É altamente recomendável que você considere todos os aplicativos quando a configuração ATP e para leitura adicional, o artigo [ATP para SharePoint, onedrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) terá informações detalhadas sobre como começar.

### <a name="safe-links"></a>Links seguros

Enquanto isso, no momento, os links seguros de proteção de ameaça avançada (ATP) não estão disponíveis no Microsoft Teams, agora eles estão em [Visualização pública](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) por meio do programa de adoção de tecnologia (toque) e, enquanto uma data de lançamento para disponibilidade geral não está definida, atualizaremos este artigo quando chegar o momento. Por enquanto, para obter informações sobre os links de segurança do Microsoft 365 ou do Office 365, reveja [links de segurança da ATP](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection). Os links seguros de ATP estão disponíveis nos planos [ATP 1 e ATP 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide).

### <a name="safe-attachments"></a>Anexos seguros

Anexos seguros é um recurso projetado para melhorar a segurança do usuário verificando e detectando anexos mal-intencionados. Os administradores de segurança ou global criam [políticas](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) para lidar com esses anexos suspeitos suspeitos para impedir que eles sejam enviados a usuários, clicados e afetados. A proteção de anexo seguro está disponível para o SharePoint Online, o OneDrive for Business e o Microsoft Teams, e o Microsoft 365 ou o Office 365 [Advanced Threat Protection plano 1 e 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) têm essa funcionalidade. Leia mais sobre os anexos seguros e como eles podem ajudar a proteger sua organização [aqui](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide).

### <a name="how-conditional-access-policies-work-for-teams"></a>Como as políticas de acesso condicional funcionam para o Teams

O Microsoft Teams depende muito do Exchange Online, do SharePoint Online e do Skype for Business online para cenários de produtividade básica, como reuniões, calendários, chats de interoperabilidade e compartilhamento de arquivos. As políticas de acesso condicional que são definidas para esses aplicativos de nuvem se aplicam ao Microsoft Teams quando um usuário entra diretamente no Microsoft Teams, em qualquer cliente.

O Microsoft Teams é compatível separadamente como um aplicativo na nuvem nas políticas de acesso condicional do Azure Active Directory. As políticas de acesso condicional definidas para o aplicativo Cloud do Microsoft Teams se aplicam ao Microsoft Teams quando um usuário entra. No entanto, sem as políticas corretas em outros aplicativos, como o Exchange Online e o SharePoint Online, os usuários ainda poderão acessar esses recursos diretamente. Para obter mais informações sobre como configurar uma política de acesso condicional no portal do Azure, acesse: [início rápido do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

Os clientes de desktop do Microsoft Teams para Windows e Mac dão suporte à autenticação moderna. A autenticação moderna traz a entrada com base na biblioteca de autenticação do Azure Active Directory (ADAL) para aplicativos cliente do Microsoft Office entre plataformas.

Aplicativo da área de trabalho do Microsoft Teams compatível com AppLocker.  Para obter mais informações sobre os pré-requisitos do AppLocker, consulte: requisitos para usar o [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Conformidade

O Microsoft Teams tem uma ampla gama de informações para ajudá-lo com áreas de conformidade, incluindo conformidade com comunicações para canais, chats e anexos, políticas de retenção, proteção contra perda de dados (DLP), descoberta eletrônica e retenção legal para canais, chats e arquivos, pesquisa de logs de auditoria, além de gerenciamento de aplicativos móveis com o Microsoft Intune. Fornecemos algumas informações sobre todos esses tópicos abaixo, e você pode acessar o centro de [conformidade do Microsoft 365](https://compliance.microsoft.com) para gerenciar essas configurações.

### <a name="information-barriers"></a>Barreiras de informação

As barreiras de informação são políticas colocadas em vigor por administradores do teams para fazer coisas como impedir que pessoas ou grupos se comuniquem umas com as outras (quando não houver necessidade de negócios para elas, ou um motivo normativo para bloqueá-las) e também permite que você defina políticas relacionadas a itens como pesquisas e descoberta eletrônica (abordadas abaixo). Essas políticas podem impactar os usuários em 1:1 chats, chats em grupo ou em um nível de equipe.

Para obter mais informações sobre este tópico, acesse [barreiras de informações no Microsoft Teams](information-barriers-in-teams.md).

### <a name="communication-compliance"></a>Conformidade com comunicações

A conformidade de comunicação no Microsoft 365 permite que você adicione usuários a políticas em escopo que podem ser configuradas para examinar comunicações do Microsoft Teams para linguagem ofensiva, informações confidenciais e informações relacionadas a padrões internos e regulamentares. Comunicações de chat e anexos associados em canais de equipes públicos e privados, chats individuais e anexos podem ser verificados para ajudar a minimizar os riscos de comunicação em sua organização. Para obter mais informações sobre como configurar políticas para ajudar você a detectar, capturar e executar ações para comunicações inadequadas a equipes, consulte [conformidade de comunicação no Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

### <a name="retention-policies"></a>Políticas de retenção

As políticas de retenção no Microsoft Teams permitem manter os dados importantes para sua organização manter, para fins regulatórios, legais, de negócios ou outros motivos e também para remover conteúdo e comunicações que não sejam relevantes para serem retidos. Você também pode usar as políticas de retenção para manter os dados por um período de tempo e, em seguida, excluí-los. Para obter mais informações, consulte o artigo sobre as [políticas de retenção no Microsoft Teams](retention-policies.md) .

### <a name="data-loss-prevention-dlp"></a>Prevenção contra perda de dados (DLP)

A prevenção contra perda de dados (DLP) no Microsoft Teams, bem como a história de DLP maior para o Microsoft 365 ou o Office 365, gira em torno da preparação para empresas quando se trata de proteger dados e documentos confidenciais. Se você tiver dúvidas quanto às informações confidenciais em mensagens ou documentos, as políticas DLP poderão ajudar a garantir que os usuários não compartilhem esses dados confidenciais com as pessoas erradas.

Para obter informações sobre a prevenção contra perda de dados no Teams, consulte [DLP para Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams). Um bom artigo para as preocupações com o O365 DLP é a [visão geral da prevenção contra perda de dados](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies).

### <a name="ediscovery"></a>eDiscovery

Descoberta eletrônica, ou descoberta eletrônica, é o aspecto eletrônico de identificar, coletar e produzir informações armazenadas eletronicamente (ESI) em resposta a uma solicitação de produção em um naipe ou uma investigação legal. Recursos incluem gerenciamento de casos, preservação, pesquisa, análise e exportação de dados do teams. Isso inclui chats, mensagens e arquivos, reuniões e resumos de chamadas. Para reuniões e chamadas do Teams, um resumo dos eventos que aconteceram na reunião e na chamada são criados e disponibilizados na descoberta eletrônica.

Para obter mais detalhes sobre como fazer o Microsoft 365 ou o Office 365 eDiscovery na central de segurança e no centro de conformidade e executar pesquisa de conteúdo de conformidade para conteúdo do Teams, acesse os links abaixo:

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[Pesquisa de conteúdo](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Temos um artigo específico do teams para obter mais informações, [descoberta eletrônica de chats convidados a convidados](eDiscovery-investigation.md).

Os clientes podem aproveitar o eDiscovery ou o [eDiscovery avançado](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) de acordo com os requisitos. As diferenças entre os dois estão destacadas na tabela a seguir:

| |eDiscovery  |Advanced eDiscovery  |
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

Consulte o artigo [visão geral do artigo sobre as políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) para saber mais sobre preservação e suspensões no centro de conformidade do Microsoft 365. Para saber mais sobre as informações específicas do teams em controle legal, também temos [o artigo colocar um usuário ou equipe do Microsoft Teams em um artigo de controle legal](legal-hold.md) para obter mais informações.

### <a name="compliance-content-search"></a>Pesquisa de conteúdo de conformidade

A pesquisa de conteúdo pode ser usada para pesquisar todos os dados do teams por meio de recursos avançados de filtragem. Os dados resultantes podem ser exportados para um contêiner específico para suporte à conformidade e litígio. Isso pode ser feito com ou sem um caso do eDiscovery. Isso permite que os administradores de conformidade coletem dados do teams em todos os usuários, analise e exporte-os para processamento adicional. Confira este artigo de [pesquisa de conteúdo](https://docs.microsoft.com/microsoft-365/compliance/content-search) para saber mais sobre como conduzir uma pesquisa de conteúdo de conformidade do Microsoft Teams e outros conteúdos do Microsoft 365 ou do Office 365 no centro de conformidade da Microsoft 365.

> [!TIP]
> Usando a pesquisa de conteúdo, você pode filtrar somente conteúdo do Microsoft Teams, como mensagens de chat e de canal, reuniões e chamadas, se necessário.

Se quiser informações específicas de outras equipes sobre como configurar a pesquisa de conteúdo, examine o artigo [Pesquisar conteúdo no Microsoft Teams](content-search.md) .

### <a name="auditing-and-reporting"></a>Auditoria e relatórios

A pesquisa de log de auditoria é conectada diretamente ao centro de conformidade do Microsoft 365 e oferece a capacidade de definir alertas, bem como relatar eventos de auditoria, permitindo a exportação de conjuntos de eventos genéricos ou de carga de trabalho para uso e investigação de administração em uma linha do tempo de auditoria ilimitada. Você pode configurar alertas para todos os dados de log de auditoria no centro de conformidade do Microsoft 365, além de filtrar e exportar esses dados para análise adicional. Consulte o artigo [Pesquisar o log de auditoria](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) para saber mais sobre como conduzir um log de auditoria para o Microsoft 365 ou o Office 365. Para saber mais sobre como Pesquisar eventos do Microsoft Teams no centro de conformidade do Microsoft 365, também temos o artigo [ativar a auditoria no artigo do teams](audit-log-events.md) para revisão.

## <a name="privacy"></a>Privacidade

Na Microsoft, a proteção dos seus dados é nossa prioridade mais alta. Para saber mais sobre nossas práticas de privacidade, leia [privacidade na Microsoft](https://www.microsoft.com/trust-center/privacy).

## <a name="information-protection-architecture"></a>Arquitetura de proteção de informações

A figura a seguir indica o fluxo de inclusão de dados do teams para os arquivos e as mensagens do Exchange e do SharePoint para Teams.

![Diagrama do fluxo de trabalho de dados do teams ao Exchange e ao SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

A figura a seguir indica o fluxo de inclusão de reuniões e dados de chamadas do teams para o Exchange.

![Diagrama do fluxo de trabalho de reuniões e dados de chamadas do teams para o Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Pode haver um atraso de 24 horas para descobrir o conteúdo das equipes.

## <a name="licensing"></a>Licenças

Quando se trata de recursos de proteção de informações, assinaturas do Microsoft 365, assinaturas do Office 365 e das licenças autônomas associadas determinarão o conjunto de recursos disponíveis.

Para obter informações sobre como determinar o licenciamento precisa implementar recursos de segurança e conformidade, consulte o [Licenciamento do Office 365 ou do Microsoft 365](https://download.microsoft.com/download/8/7/7/877B1713-671E-43AA-BB79-AF8478C64AFF/Licensing-Microsoft-365.pdf).

> [!NOTE]
> A pesquisa de conteúdo e a descoberta eletrônica não precisam ser habilitadas no centro de conformidade do & de segurança para funcionar.

## <a name="location-of-data-in-teams"></a>Localização dos dados no Microsoft Teams

Os dados do teams residem na região geográfica associada à sua organização do Microsoft 365 ou do Office 365. Para ver em quais regiões há suporte no momento, examine a [localização dos dados no Microsoft Teams](location-of-data-in-teams.md).

Se você precisar ver qual região abriga os dados para o seu locatário, vá para o perfil da organização de configurações do [centro de administração do Microsoft 365](https://portal.office.com/adminportal/home)  >  **Settings**  >  **Organization profile**. Role para baixo até **Local dos dados**.

![Captura de tela da tabela de localização de dados, incluindo equipes no centro de administração](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Padrões de conformidade

O Teams usa os seguintes padrões: [iso 27001](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001), [ISO 27018](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018), [SSAE16 SOC 1 e SOC 2](https://docs.microsoft.com/microsoft-365/compliance/offering-soc), [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)e [cláusulas de modelo da União Europeia (EUMC)](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses). Na Microsoft Compliance Framework, a Microsoft classifica os aplicativos e serviços do Microsoft 365 e do Office 365 em quatro categorias. Cada categoria é definida por compromissos de conformidade específicos que devem ser atendidos para um serviço do Microsoft 365 ou do Office 365, ou um serviço da Microsoft relacionado, para serem listados nessa categoria.

Os detalhes podem ser encontrados nos [recursos de proteção de dados](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides). O Microsoft Teams também dá suporte à conformidade com o Cloud Security Alliance.

## <a name="related-topics"></a>Tópicos relacionados

Segurança do Microsoft [365](https://docs.microsoft.com/microsoft-365/security/) 
 Conformidade com o [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/) 
 [Ofertas de conformidade da Microsoft](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
