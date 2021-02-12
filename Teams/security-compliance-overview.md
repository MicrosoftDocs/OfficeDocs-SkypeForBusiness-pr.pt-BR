---
title: Visão geral de segurança e conformidade
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Uma visão geral dos recursos de segurança e conformidade do Microsoft Teams, incluindo privacidade e criptografia, auditoria e relatórios e muito mais.
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
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c400f6f3fdb0c0cf5abce3a34f05c8488909aab
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122201"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Segurança e conformidade no Microsoft Teams

> [!IMPORTANT]
> Para saber como garantir melhor a segurança enquanto todos trabalham em casa durante a epidemia de **COVID-19,** leia estes artigos:
>  - [As 12 principais tarefas para as equipes de segurança dar suporte ao trabalho em casa](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Otimize a conectividade do Microsoft 365 ou do Office 365 para usuários remotos usando o tunelamento dividido da VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Atualizado em 2 de abril de 2020: Guia [de segurança do Teams](teams-security-guide.md)


O Microsoft Teams é criado na nuvem de nível empresarial de nível empresarial e de hiper escala do Microsoft 365 e do Office 365, fornecendo os recursos avançados de segurança e conformidade que nossos clientes esperam. Para saber mais sobre o planejamento de segurança no Microsoft [](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) 365 ou no Office 365, o roteiro de segurança é um bom lugar para começar. Para obter mais informações sobre o planejamento de conformidade no Microsoft 365 ou no Office 365, você pode começar com o Plano de conformidade & [segurança.](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)


Este artigo fornecerá mais informações sobre segurança e conformidade específicas do Teams. Não perca estes vídeos da Microsoft Mechanics sobre segurança e conformidade:

- [Microsoft Teams Essentials para IT: Segurança e Conformidade](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Controles do Microsoft Teams para Segurança e Conformidade](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> Como cliente do Microsoft 365 ou do Office 365, você possui e controla seus dados. A Microsoft não usa seus dados para nenhum outro fim, além de lhe fornecer o serviço ao qual você se inscreveu. Como um provedor de serviços, não examinamos seu e-mail, seus documentos nem suas equipes para publicidade ou propósitos que não estejam relacionados ao serviço. A Microsoft não tem acesso ao conteúdo carregado. Como o OneDrive e o SharePoint no Microsoft 365, os dados do cliente permanecem dentro do locatário. Você pode conferir mais sobre nossas informações relacionadas à confiança e segurança na [Central de Confiações da Microsoft.](https://microsoft.com/trustcenter) O Teams segue as mesmas diretrizes e princípios que a Central de Confiabilidade da Microsoft.

## <a name="security"></a>Segurança

O Teams impõe a autenticação de dois fatores em toda a equipe e em toda a organização, o login único por meio do Active Directory e a criptografia de dados em trânsito e em repouso. Os arquivos ficam armazenados no SharePoint e são respaldados pela criptografia do SharePoint. As notas ficam armazenadas no OneNote e são respaldadas pela criptografia do OneNote. Os dados do OneNote são armazenados no site do SharePoint da equipe. A guia Wiki também pode ser usada para fazer anotações e seu conteúdo também é armazenado no site do SharePoint da equipe.

Leia [modelos de identidade e autenticação](identify-models-authentication.md) para [](sign-in-teams.md) obter mais informações sobre autenticação e Equipes, e como funciona a autenticação moderna ajudará com a autenticação moderna em particular.

Como o Teams trabalha em parceria com o SharePoint, o OneNote, o Exchange e muito mais, você deve se sentir à vontade para gerenciar a segurança no Microsoft 365 ou office 365. Para saber mais, leia sobre como configurar sua organização do [Microsoft 365 ou office 365 para aumentar a segurança.](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)

> [!NOTE]
> Atualmente, os canais [privados são compatíveis](private-channels.md) com recursos limitados de segurança e conformidade. O suporte para todo o conjunto de recursos de segurança e conformidade em canais privados estará em breve.

### <a name="advanced-threat-protection-atp"></a>Proteção Avançada contra Ameaças (ATP)

A Proteção Avançada contra Ameaças (ATP) está disponível para o Microsoft Teams, juntamente com o SharePoint e o OneDrive, aplicativos que se integram ao Teams para gerenciamento de conteúdo. A ATP permite determinar se o conteúdo nesses aplicativos é mal-intencionado por natureza e bloquear esse conteúdo do acesso do usuário.

Como o conteúdo afetado é gerenciado após a detecção está nas configurações selecionadas no Microsoft 365 ou no Office 365. Recomendamos que você considere todos os aplicativos quando se trata de configurar a ATP e, para leitura posterior, a ATP para [SharePoint, o OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) e o Microsoft Teams terão informações detalhadas sobre como começar.

### <a name="safe-links"></a>Links Seguros

Embora, no momento, os links seguros da Proteção Avançada contra Ameaças (ATP) não estão disponíveis no Microsoft Teams, agora eles estão em visualização pública por meio do nosso Programa de Adoção de Tecnologia (TAP) e, embora não seja definida uma data de lançamento para disponibilidade geral, atualizaremos este artigo quando chegar a hora. [](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) Enquanto isso, para obter informações sobre Links Seguros do Microsoft 365 ou Office 365, consulte [Links Seguros da ATP.](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection) Links seguros da ATP estão disponíveis no [Plano ATP 1 e no Plano ATP 2.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)

### <a name="safe-attachments"></a>Anexos Seguros

Anexos seguros é um recurso projetado para aprimorar a segurança do usuário verificando e detectando anexos mal-intencionados. Administradores globais ou [](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) de segurança criam políticas para lidar com esses anexos suspeitos mal-intencionados para impedir que eles seja enviados aos usuários, clicados e agidos. A proteção de anexos seguros está disponível para que o SharePoint, o OneDrive e o Microsoft Teams e o Microsoft 365 ou o Office 365 [Advanced Threat Protection Plan 1](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) e 2 tenham esse recurso. Leia mais sobre Anexos Seguros e como eles podem ajudar a proteger sua organização em Anexos Seguros [no Microsoft Defender para Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="secure-score"></a>Pontuação Segura

A Pontuação Segura da Microsoft é uma medida da postura de segurança de uma organização, com um número maior indicando mais ações de melhoria realizadas. Ele pode ser encontrado no centro [de segurança do Microsoft 365.](https://security.microsoft.com/securescore) Seguir as recomendações de Pontuação Segura pode proteger sua organização contra ameaças. Em um painel centralizado na central de segurança do Microsoft 365, as organizações podem monitorar e trabalhar na segurança de identidades, aplicativos e dispositivos do Microsoft 365. O Microsoft Teams agora tem recomendações sobre a Pontuação Segura, e os administradores são incentivados a monitorar sua política de segurança na plataforma.

A Pontuação Segura ajuda as organizações:
- Relatório sobre o estado atual da postura de segurança da organização.
- Melhore a postura de segurança fornecendo capacidade de descoberta, visibilidade, orientação e controle.
- Compare com os parâmetros de referência e estabeleça KPIs (indicadores chave de desempenho).


### <a name="how-conditional-access-policies-work-for-teams"></a>Como funcionam as políticas de Acesso Condicional para o Teams

O Microsoft Teams depende muito do Exchange Online, do SharePoint e do Skype for Business Online para cenários de produtividade principais, como reuniões, calendários, chats interop e compartilhamento de arquivos. As políticas de acesso condicional definidas para esses aplicativos de nuvem se aplicam ao Microsoft Teams quando um usuário entrar diretamente no Microsoft Teams em qualquer cliente.

O Microsoft Teams tem suporte separadamente como um aplicativo de nuvem nas políticas de acesso condicional do Azure Active Directory. As políticas de acesso condicional definidas para o aplicativo de nuvem do Microsoft Teams se aplicam ao Microsoft Teams quando um usuário entrar. No entanto, sem as políticas corretas em outros aplicativos, como o Exchange Online e o SharePoint, os usuários ainda poderão acessar esses recursos diretamente. Para obter mais informações sobre como configurar uma política de acesso condicional no portal do Azure, consulte o Início Rápido do [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Os clientes da área de trabalho do Microsoft Teams para Windows e Mac são suportados pela autenticação moderna. A autenticação moderna traz a entrada com base na ADAL (Biblioteca de Autenticação do Azure Active Directory) para aplicativos cliente do Microsoft Office em todas as plataformas.

O aplicativo da área de trabalho do Microsoft Teams dá suporte ao AppLocker.  Para obter mais informações sobre pré-requisitos do AppLocker, consulte: Requisitos para usar [o AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)

## <a name="compliance"></a>Conformidade

O Teams tem uma ampla variedade de informações para ajudá-lo com áreas de conformidade, incluindo a conformidade de comunicação para canais, chats e anexos, políticas de retenção, DLP (Proteção contra Perda de Dados), Descobertas e retenção legal para canais, chats e arquivos, pesquisa de log de auditoria, bem como gerenciamento de aplicativos móveis com o Microsoft Intune. Fornecemos algumas informações sobre todos esses tópicos abaixo e você pode ir para o centro de conformidade do [Microsoft 365](https://compliance.microsoft.com) para gerenciar essas configurações.

### <a name="information-barriers"></a>Barreiras de informações

Barreiras de informações são políticas colocadas em uso pelos administradores do Teams para fazer coisas como impedir que pessoas ou grupos se comuniquem entre si (quando não há necessidade comercial para que eles o façam, ou um motivo regulamentar para impedi-los de fazê-lo) e também permite definir políticas relacionadas a coisas como pesquisa e Descobertas EDiscovery (cobertas abaixo). Essas políticas podem afetar os usuários em chats entre duas pessoas, chats em grupo ou em um nível de equipe.

Para ler mais sobre este tópico, vá para [Barreiras de informações no Microsoft Teams.](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>Conformidade de comunicação

A conformidade de comunicação no Microsoft 365 permite adicionar usuários a políticas de escopo que podem ser configuradas para examinar as comunicações do Microsoft Teams em busca de linguagem ofensiva, informações confidenciais e informações relacionadas a padrões internos e regulatórios. As comunicações de chat e anexos associados em canais públicos e privados do Teams, chats individuais e anexos podem ser verificados para ajudar a minimizar os riscos de comunicação em sua organização. Para saber mais sobre como configurar políticas para ajudá-lo a detectar, capturar e tomar medidas para comunicações inadequadas do Teams, consulte Conformidade de comunicação no [Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)

### <a name="retention-policies"></a>Políticas de retenção

As políticas de retenção no Microsoft Teams permitem manter os dados que são importantes para sua organização, por motivos regulatórios, jurídicos, comerciais ou outros, e também para remover conteúdo e comunicações que não são relevantes para serem retidos. Você também pode usar políticas de retenção para manter os dados por um período e depois excluí-los. Para obter mais informações, revise [as políticas de retenção no Microsoft Teams.](retention-policies.md)

## <a name="sensitivity-labels"></a>Rótulos de sensibilidade

Aplique [rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) para proteger e regular o acesso a conteúdo organizacional sensível criado durante a colaboração dentro das equipes. Por exemplo, aplique rótulos que configurem a privacidade (pública ou privada) das equipes, controlem o acesso de convidados e o compartilhamento externo e gerenciem o acesso de dispositivos não gerenciadas. Para obter mais informações, revise [os rótulos de sensibilidade no Microsoft Teams.](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>Prevenção contra Perda de Dados (DLP)

A Prevenção contra Perda de Dados (DLP) no Microsoft Teams, bem como a história DLP maior do Microsoft 365 ou do Office 365, gira em torno da preparação comercial quando se trata de proteger documentos e dados confidenciais. Se você tiver dúvidas sobre informações confidenciais em mensagens ou documentos, as políticas DLP poderão ajudar a garantir que seus usuários não compartilhem esses dados confidenciais com as pessoas erradas.

Para obter informações sobre a Prevenção contra Perda de Dados no Teams, revise [a DLP do Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams) Um bom artigo sobre as preocupações da DLP do O365 é Uma visão [geral da prevenção contra perda de dados.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>Descoberta eletrônica

Descoberta eletrônica, ou Descoberta Eletrônica, é o aspecto eletrônico de identificar, coletar e produzir informações armazenadas eletronicamente (ESI) em resposta a uma solicitação de produção em um processo legal ou investigação. Os recursos incluem gerenciamento de casos, preservação, pesquisa, análise e exportação de dados do Teams. Isso inclui chat, mensagens e arquivos, resumos de reunião e chamada. Para reuniões e Chamadas do Teams, um resumo dos eventos que aconteceram na reunião e na chamada são criados e disponibilizados na Descoberta Telefônica.

Para obter mais detalhes sobre como fazer a Descoberta Online do Microsoft 365 ou office 365 no centro de segurança e no centro de conformidade e executar a pesquisa de conteúdo de conformidade para conteúdo do Teams, acesse os links abaixo:

 - [Descoberta eletrônica](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

 - [Pesquisa de Conteúdo](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Temos um artigo específico do Teams para obter mais informações, Descoberta e Descoberta De chats de [convidado para convidado.](eDiscovery-investigation.md)

Os clientes podem aproveitar a Descoberta Ediscovery ou [a Descoberta Avançada de](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) acordo com suas necessidades. As diferenças entre os dois estão destacadas na tabela a seguir:

| |Descoberta eletrônica  |Advanced eDiscovery  |
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

Durante o litígio, você pode precisar que todos os dados associados a um usuário (sédiano) ou a uma Equipe sejam preservados como imutáveis, para que possam ser usados como evidências para o caso. Você pode fazer isso colocando um usuário (caixa de correio do usuário) ou uma Equipe em espera legal. Para uma responsabilidade legal da equipe, a caixa de correio da equipe pode ser colocada nas seguintes retém:

- In-Place (um subconjunto da caixa de correio ou do conjunto de sites por meio de consultas direcionadas ou conteúdo filtrado é colocado em espera) ou
- Contenção de Litígio (toda a caixa de correio ou conjunto de sites é colocada em responsabilidade).

Em ambos os casos, uma vez definida a responsabilidade, ela garante que, mesmo que os usuários finais excluam ou editem mensagens de canal que estão na caixa de correio do grupo, cópias imutáveis desse conteúdo são mantidas e disponíveis por meio da pesquisa de Descoberta Eletrônico. Em geral, as rescuições legais são aplicadas no contexto de um caso de DescobertaScobrida.

Confira a [Visão geral das políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) para entender mais sobre preservação e retenções no Centro de conformidade do Microsoft 365. Para obter mais informações específicas do Teams sobre a responsabilidade legal, também temos a opção Colocar um usuário ou equipe do [Microsoft Teams](legal-hold.md) em responsabilidade legal para que você saiba mais.

### <a name="compliance-content-search"></a>Pesquisa de conteúdo de conformidade

A pesquisa de conteúdo pode ser usada para pesquisar todos os dados do Teams por meio de recursos avançados de filtragem. Os dados resultantes podem ser exportados para um contêiner específico para suporte a conformidade e litígio. Isso pode ser feito com ou sem um caso do eDiscovery. Isso permite que os administradores de conformidade reúnam dados do Teams em todos os usuários, revisem e exportem-os para processamento posterior. Consulte a [](https://docs.microsoft.com/microsoft-365/compliance/content-search) Pesquisa de Conteúdo para saber mais sobre como realizar uma pesquisa de conteúdo de conformidade para o Microsoft Teams e outro conteúdo do Microsoft 365 ou do Office 365 no Centro de conformidade do Microsoft 365.

> [!TIP]
> Usando a pesquisa de conteúdo, você pode filtrar para baixo até o conteúdo somente do Microsoft Teams, como Mensagens de Chat e Canal, Reuniões e Chamadas, se necessário.

Se você quiser mais informações específicas do Teams sobre como configurar a pesquisa de conteúdo, revise a [pesquisa de conteúdo no Microsoft Teams.](content-search.md)

### <a name="auditing-and-reporting"></a>Auditoria e relatórios

A pesquisa de log de auditoria conecta-se ao Centro de conformidade do Microsoft 365 e oferece a capacidade de definir alertas, bem como relatório sobre eventos de auditoria, permitindo a exportação de conjuntos de eventos específicos ou genéricos de carga de trabalho para uso e investigação do administrador em uma linha do tempo de auditoria ilimitada. Você pode configurar alertas para todos os dados do Log de auditoria no Centro de conformidade do Microsoft 365 e filtrar e exportar esses dados para análise posterior. Consulte Pesquisar [o log de auditoria](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) para saber mais sobre como realizar uma pesquisa de log de auditoria do Microsoft 365 ou do Office 365. Para saber mais sobre como pesquisar eventos do Microsoft Teams no Centro de conformidade do Microsoft 365, também temos adoção da auditoria no [Teams](audit-log-events.md) para você revisar.

## <a name="customer-key"></a>Chave do Cliente

O Microsoft 365 oferece uma camada adicional de criptografia sobre a criptografia de serviço para seu conteúdo. Usando chaves fornecidas, a Chave do Cliente criptografa vários tipos diferentes de dados no Microsoft Teams. Usando a Chave do Cliente no nível do aplicativo, a Chave do Cliente criptografa arquivos do Teams armazenados no SharePoint Online. Para obter informações, consulte [Criptografia de serviço com a Chave do Cliente.](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) 

Usando a Chave do Cliente no nível do locatário, a Chave do Cliente criptografa:
- Mensagens de chat do Teams (chats entre duas pessoas, chats em grupo, chats de reunião e conversas de canal)
- Mensagens de mídia do Teams (imagens, trechos de código, vídeos e imagens wiki)
- Gravações de chamada e reunião do Teams armazenadas no armazenamento do Teams
- Notificações de chat do Teams
- Sugestões de chat do Teams pela Cortana
- Mensagens de status do Teams Para obter mais informações, consulte Visão geral da Chave do Cliente do [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level) no nível do locatário e leia o blog do Microsoft Teams que aborda o suporte à Chave do Cliente do Microsoft Teams agora na Visualização [Pública.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893) Para obter informações sobre a versão da Proteção de Informações da Microsoft que incluía a Chave do Cliente no nível do locatário, leia Anunciando novos recursos da Proteção de Informações da Microsoft para conhecer e proteger [seus dados confidenciais.](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)

## <a name="privacy"></a>Privacidade

Na Microsoft, proteger seus dados é nossa prioridade mais alta. Para saber mais sobre nossas práticas de privacidade, leia:  

- [Privacidade na Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Nosso compromisso com a privacidade e segurança no Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Para profissionais de TI: privacidade e segurança no Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Arquitetura de Proteção de Informações

A figura a seguir indica o fluxo de ingestão de dados do Teams para o Exchange e o SharePoint para Arquivos e Mensagens do Teams.

> [!div class="mx-imgBorder"]
> ![Diagrama do fluxo de trabalho de dados do Teams para o Exchange e o SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

A figura a seguir indica o fluxo de ingestão de Reuniões do Teams e a chamada de dados para o Exchange.

> [!div class="mx-imgBorder"]
> ![Diagrama do fluxo de trabalho de Reuniões do Teams e dados de chamada para o Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Pode haver até 24 horas para descobrir o conteúdo do Teams.

## <a name="licensing"></a>Licenciamento

Quando se trata de recursos de proteção de informações, as assinaturas do Microsoft 365, as assinaturas do Office 365 e as licenças autônomas associadas determinarão o conjunto de recursos disponíveis.

Para obter informações sobre como determinar as necessidades de licenciamento [](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) para implementar recursos de segurança e conformidade, revise os requisitos de licenciamento para recursos de segurança e conformidade.

> [!NOTE]
> A Pesquisa de Conteúdo e a Descoberta Digital não precisam ser habilitadas no Centro de Conformidade & segurança para funcionar.

## <a name="location-of-data-in-teams"></a>Localização dos dados no Microsoft Teams

No Teams, os dados são armazenados na região geográfica associada à sua organização do Microsoft 365 ou do Office 365. Para ver quais regiões têm suporte no momento, revise a [localização dos dados no Microsoft Teams.](location-of-data-in-teams.md)

Se você precisar ver qual região tem dados para seu locatário, vá para o perfil de Organização do Centro de administração do [Microsoft 365.](https://portal.office.com/adminportal/home)  >    >   Role para baixo até **Localização de dados**.

> [!div class="mx-imgBorder"]
> ![Captura de tela da tabela De localização de dados, incluindo o Teams no centro de administração](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Padrões de conformidade

O Teams usa os seguintes padrões: [ISO 27001,](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001) [ISO 27018,](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018) [SSAE18 SOC 1 e SOC 2,](https://docs.microsoft.com/microsoft-365/compliance/offering-soc) [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)e cláusulas de modelo [da UE (EUMC).](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses) Dentro da estrutura de conformidade da Microsoft, a Microsoft classifica os aplicativos e serviços do Microsoft 365 e do Office 365 em quatro categorias. Cada categoria é definida por compromissos de conformidade específicos que devem ser atendidos para que um serviço do Microsoft 365 ou do Office 365 ou um serviço relacionado da Microsoft seja listado nessa categoria.

Os detalhes podem ser encontrados nos [Recursos de Proteção de Dados.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) O Microsoft Teams também dá suporte à conformidade com o Cloud Security Alliance.

## <a name="related-topics"></a>Tópicos relacionados

[Segurança do Microsoft 365](https://docs.microsoft.com/microsoft-365/security/)

[Conformidade do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/)

[Ofertas de conformidade da Microsoft](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
