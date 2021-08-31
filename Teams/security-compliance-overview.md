---
title: Visão geral da segurança e conformidade
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Uma visão geral dos Microsoft Teams de segurança e conformidade, incluindo privacidade e criptografia, auditoria e relatórios e muito mais.
ms.localizationpriority: medium
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
ms.openlocfilehash: 61a6cba9ff05e6ee088c96231e8eb947e5d56fed
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733160"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Segurança e conformidade em Microsoft Teams

> [!IMPORTANT]
> Para saber como garantir melhor a segurança enquanto todos trabalham em casa durante a epidemia do **COVID-19,** leia estes artigos:
>  - [As 12 principais tarefas para as equipes de segurança dar suporte ao trabalho em casa](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Otimize a conectividade do Microsoft 365 ou do Office 365 para usuários remotos usando o tunelamento dividido da VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Atualizado em 2 de abril de 2020: [Teams guia de segurança](teams-security-guide.md)


Microsoft Teams é criado com base no Microsoft 365 e Office 365 hiper escala, nuvem de nível empresarial, fornecendo os recursos avançados de segurança e conformidade que nossos clientes esperam. Para obter mais informações sobre o planejamento de segurança Microsoft 365 ou [Office 365,](/microsoft-365/security/office-365-security/security-roadmap) o roteiro de segurança é um bom lugar para começar. Para obter mais informações sobre o planejamento de conformidade Microsoft 365 ou Office 365, você pode começar com [Plan for security & compliance](/microsoft-365/compliance/plan-for-security-and-compliance).


Este artigo fornecerá mais informações sobre Teams segurança e conformidade específicas. Não perca estes vídeos do Microsoft Mechanics sobre segurança e conformidade:

- [Microsoft Teams Essentials for IT: Segurança e Conformidade](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Microsoft Teams controles para segurança e conformidade](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> Como cliente de Microsoft 365 ou Office 365, você possui e controla seus dados. A Microsoft não usa seus dados para nenhum outro fim, além de lhe fornecer o serviço ao qual você se inscreveu. Como um provedor de serviços, não examinamos seu e-mail, seus documentos nem suas equipes para publicidade ou propósitos que não estejam relacionados ao serviço. A Microsoft não tem acesso ao conteúdo carregado. Como OneDrive e SharePoint no Microsoft 365, os dados do cliente permanecem dentro do locatário. Você pode conferir mais sobre nossas informações relacionadas à segurança e confiança na [Central de Confiações da Microsoft.](https://microsoft.com/trustcenter) Teams segue as mesmas diretrizes e princípios que a Central de Confiabilidade da Microsoft.

## <a name="security"></a>Segurança

Teams impõe a autenticação de dois fatores em toda a equipe e na organização, o login único por meio do Active Directory e a criptografia de dados em trânsito e em repouso. Os arquivos ficam armazenados no SharePoint e são respaldados pela criptografia do SharePoint. As notas ficam armazenadas no OneNote e são respaldadas pela criptografia do OneNote. Os OneNote de dados são armazenados no site SharePoint equipe. A guia Wiki também pode ser usada para anotações e seu conteúdo também é armazenado no site de SharePoint equipe.

Leia [Modelos de identidade e autenticação](identify-models-authentication.md) para obter [](sign-in-teams.md) mais informações sobre autenticação e Teams e Como a autenticação moderna funciona ajudará com a autenticação moderna em particular.

Como Teams funciona em parceria com SharePoint, OneNote, Exchange e muito mais, você deve estar confortável gerenciando a segurança no Microsoft 365 ou Office 365 tudo. Para saber mais, leia sobre como configurar seu Microsoft 365 [ou Office 365 para aumentar a segurança.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)

> [!NOTE]
> Atualmente, os [canais privados suportam](private-channels.md) recursos limitados de segurança e conformidade. O suporte para o conjunto completo de recursos de segurança e conformidade em canais privados está chegando em breve.

### <a name="advanced-threat-protection-atp"></a>Proteção Avançada contra Ameaças (ATP)

A Proteção Avançada contra Ameaças (ATP) está disponível para Microsoft Teams, juntamente com SharePoint e OneDrive, aplicativos que se integram ao Teams para gerenciamento de conteúdo. A ATP permite determinar se o conteúdo nesses aplicativos é mal-intencionado por natureza e bloquear esse conteúdo do acesso do usuário.

Como o conteúdo afetado é gerenciado após a detecção é de acordo com as configurações selecionadas em Microsoft 365 ou Office 365. Recomendamos que você considere todos os aplicativos quando se trata de configurar a ATP e, para leitura mais detalhada, a ATP para [SharePoint, OneDrive](/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) e Microsoft Teams terá informações detalhadas sobre como começar.

### <a name="safe-links"></a>Cofre Links

Embora, no momento, os links seguros da Proteção Avançada contra Ameaças (ATP) [](/microsoft-365/security/office-365-security/atp-safe-links-for-teams) não estão disponíveis no Microsoft Teams, eles agora estão em visualização pública por meio do nosso Programa de Adoção de Tecnologia (TAP) e, embora uma data de lançamento para disponibilidade geral não seja definida, atualizaremos este artigo quando essa hora chegar. Enquanto isso, para obter informações sobre Microsoft 365 ou Office 365 Cofre Links, consulte [ATP Cofre Links](/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection). Os Cofre ATP estão disponíveis no Plano [1 da ATP e no Plano ATP 2](/microsoft-365/security/office-365-security/office-365-atp).

### <a name="safe-attachments"></a>Cofre Anexos

Cofre anexos é um recurso projetado para aprimorar a segurança do usuário verificando e detectando anexos mal-intencionados. Administradores globais ou [](/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies) de segurança criam políticas para lidar com esses anexos mal-intencionados suspeitos para impedir que eles são enviados aos usuários, clicados e agidos. Cofre proteção de anexos está disponível para SharePoint, OneDrive e Microsoft Teams e Microsoft 365 ou Office 365 Plano [1](/microsoft-365/security/office-365-security/office-365-atp) e 2 de Proteção Avançada contra Ameaças 1 e 2 têm essa funcionalidade. Leia mais sobre Cofre anexos e como eles podem ajudar a proteger sua organização em Cofre [Anexos](/microsoft-365/security/office-365-security/atp-safe-attachments)no Microsoft Defender para Office 365 .

### <a name="secure-score"></a>Pontuação Segura

A Pontuação Segura da Microsoft é uma medida da postura de segurança de uma organização, com um número maior indicando mais ações de melhoria realizadas. Ele pode ser encontrado no centro [de Microsoft 365 de segurança](https://security.microsoft.com/securescore). Seguir as recomendações de Pontuação Segura pode proteger sua organização contra ameaças. Em um painel centralizado no centro de segurança Microsoft 365, as organizações podem monitorar e trabalhar na segurança de suas identidades, aplicativos e dispositivos Microsoft 365 segurança. Microsoft Teams agora tem recomendações sobre a Pontuação Segura e os administradores são incentivados a monitorar sua posição de segurança na plataforma.

A Pontuação Segura ajuda as organizações:
- Relatório sobre o estado atual da postura de segurança da organização.
- Melhore a postura de segurança fornecendo capacidade de descoberta, visibilidade, orientação e controle.
- Compare com os parâmetros de referência e estabeleça os principais indicadores de desempenho (KPIs).


### <a name="how-conditional-access-policies-work-for-teams"></a>Como as políticas de Acesso Condicional funcionam para Teams

Microsoft Teams depende muito do Exchange Online, SharePoint e Skype for Business Online para cenários de produtividade principais, como reuniões, calendários, chats de interop e compartilhamento de arquivos. As políticas de acesso condicional definidas para esses aplicativos de nuvem se aplicam Microsoft Teams quando um usuário entrar diretamente Microsoft Teams em qualquer cliente.

Microsoft Teams é suportado separadamente como um aplicativo de nuvem Azure Active Directory políticas de acesso condicional. As políticas de acesso condicional definidas para o aplicativo Microsoft Teams nuvem se aplicam Microsoft Teams quando um usuário se instala. No entanto, sem as políticas corretas em outros aplicativos, como Exchange Online e SharePoint, os usuários ainda poderão acessar esses recursos diretamente. Para obter mais informações sobre como configurar uma política de acesso condicional no portal do Azure, consulte [Azure Active Directory Início Rápido.](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Microsoft Teams clientes de área de trabalho para Windows e Mac suportam autenticação moderna. A autenticação moderna traz entrada com base na biblioteca Azure Active Directory autenticação (ADAL) para Microsoft Office aplicativos cliente em plataformas.

Microsoft Teams aplicativo da área de trabalho oferece suporte ao AppLocker.  Para obter mais informações sobre os pré-requisitos do AppLocker, consulte: Requisitos para usar [o AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Conformidade

Teams tem uma ampla variedade de informações para ajudá-lo com áreas de conformidade, incluindo conformidade de comunicação para canais, chats e anexos, políticas de retenção, Proteção contra Perda de Dados (DLP), Descoberta e retenção legal para canais, chats e arquivos, pesquisa de log de auditoria, bem como gerenciamento de aplicativos móveis com Microsoft Intune. Fornecemos algumas informações sobre todos esses tópicos abaixo e você pode ir para o Centro de conformidade do Microsoft 365 [gerenciar](https://compliance.microsoft.com) essas configurações.

### <a name="information-barriers"></a>Barreiras de informações

As barreiras de informações são políticas colocadas no local pelos administradores do Teams para fazer coisas como impedir que pessoas ou grupos se comuniquem entre si (quando não há necessidade comercial de fazê-lo, ou um motivo regulamentar para impedi-los de fazê-lo) e também permite que você desempacove políticas relacionadas a coisas como pesquisa e Descoberta eDiscovery (abordada abaixo). Essas políticas podem afetar os usuários em chats 1:1, chats em grupo ou em nível de equipe. O recurso Barreira de Informações está disponível na nuvem pública e, a partir de janeiro de 2021, ele foi lançado para a GCC nuvem.

Para obter mais leitura sobre este tópico, acesse [Barreiras de informações em Microsoft Teams](information-barriers-in-teams.md).

### <a name="communication-compliance"></a>Conformidade de comunicações

A conformidade de comunicação Microsoft 365 permite adicionar usuários a políticas no escopo que podem ser configuradas para examinar as comunicações Microsoft Teams de linguagem ofensiva, informações confidenciais e informações relacionadas a padrões internos e regulatórios. Comunicações de chat e anexos associados em canais públicos e privados Teams, chats individuais e anexos podem ser verificados para ajudar a minimizar os riscos de comunicação em sua organização. Para obter mais informações sobre como você pode configurar políticas para ajudá-lo a detectar, capturar e tomar medidas para comunicações Teams inadequadas, consulte Conformidade de comunicação [em Microsoft 365](/microsoft-365/compliance/communication-compliance).

### <a name="retention-policies"></a>Políticas de retenção

As políticas de retenção no Microsoft Teams permitem que você retenha dados que são importantes para sua organização manter, por motivos regulatórios, legais, comerciais ou outros, e também para remover conteúdo e comunicações que não são relevantes para serem mantidos. Você também pode usar políticas de retenção para manter os dados por um período de tempo e excluí-los. Para obter mais informações, revise [as políticas de retenção em Microsoft Teams](retention-policies.md).

## <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Aplique [rótulos de sensibilidade](/microsoft-365/compliance/sensitivity-labels) para proteger e regular o acesso a conteúdo organizacional sensível criado durante a colaboração nas equipes. Por exemplo, aplique rótulos que configurem a privacidade (pública ou privada) das equipes, controlem o acesso de convidados e o compartilhamento externo e gerenciem o acesso de dispositivos não gerenciadas. Para obter mais informações, revise [rótulos de sensibilidade em Microsoft Teams](sensitivity-labels.md).

### <a name="data-loss-prevention-dlp"></a>Prevenção contra Perda de Dados (DLP)

A prevenção contra perda de dados (DLP) no Microsoft Teams, bem como a história de DLP maior para Microsoft 365 ou Office 365, gira em torno da preparação dos negócios quando se trata de proteger documentos e dados confidenciais. Se você tiver preocupações com informações confidenciais em mensagens ou documentos, as políticas de DLP poderão ajudar a garantir que os usuários não compartilhem esses dados confidenciais com as pessoas erradas.

Para obter informações sobre Prevenção contra Perda de Dados Teams, consulte [DLP para Microsoft Teams](/microsoft-365/compliance/dlp-microsoft-teams). Um bom artigo para as preocupações de DLP do O365 é [Visão geral da prevenção contra perda de dados.](/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>Descoberta Eletrônica

A descoberta eletrônica, ou Descoberta Eletrônica, é o aspecto eletrônico de identificar, coletar e produzir informações armazenadas eletronicamente (ESI) em resposta a uma solicitação de produção em uma ação de lei ou investigação. Os recursos incluem gerenciamento de caso, preservação, pesquisa, análise e exportação de Teams dados. Isso inclui chat, mensagens e arquivos, resumos de reuniões e de chamada. Para Teams reuniões e chamadas, um resumo dos eventos que aconteceram na reunião e na chamada são criados e disponibilizados na Descoberta EDiscovery.

Para obter mais detalhes sobre como fazer Microsoft 365 ou Office 365 Descoberta Office 365 no centro de segurança e no centro de conformidade e executar a pesquisa de conteúdo de conformidade para Teams conteúdo, acesse os links abaixo:

 - [eDiscovery](/microsoft-365/compliance/manage-legal-investigations)

 - [Pesquisa de Conteúdo](/microsoft-365/compliance/search-for-content)

Temos um Teams específico para obter mais informações, [Descoberta eDiscovery de chats de convidados para convidados.](eDiscovery-investigation.md)

Os clientes podem aproveitar a Descoberta Advanced eDiscovery de [acordo](/microsoft-365/compliance/office-365-advanced-ediscovery) com seus requisitos. As diferenças entre os dois estão destacadas na tabela a seguir:

|&nbsp; |Descoberta Eletrônica  |Advanced eDiscovery  |
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

Durante o litígio, você pode precisar que todos os dados associados a um usuário (custodiante) ou a uma Equipe sejam preservados como imutáveis, para que possam ser usados como evidência para o caso. Você pode fazer isso colocando um usuário (caixa de correio de usuário) ou uma Equipe em espera legal. Para uma responsabilidade legal da equipe, a caixa de correio da equipe pode ser colocada nos seguintes resdados:

- In-Place de espera (um subconjunto da caixa de correio ou do conjunto de sites por meio de consultas direcionadas ou conteúdo filtrado é colocado em espera) ou
- Recolhimento de litígio (toda a caixa de correio ou conjunto de sites é colocado em espera).

Em ambos os casos, uma vez definida a isenção, ela garante que, mesmo que os usuários finais excluam ou editem mensagens de canal que estão na caixa de correio do grupo, cópias imutáveis desse conteúdo são mantidas e disponíveis por meio da pesquisa de Descoberta Eletrônico. Os ressamentos legais geralmente são aplicados no contexto de um caso de Descoberta e.

Consulte [Overview of retention policies](/microsoft-365/compliance/retention-policies) to understand more about preservation and holds in the Centro de conformidade do Microsoft 365. Para obter Teams informações específicas sobre a responsabilidade legal, também temos [Place a](legal-hold.md) Microsoft Teams usuário ou equipe em espera legal para que você saiba mais.

### <a name="compliance-content-search"></a>Pesquisa de conteúdo de conformidade

A pesquisa de conteúdo pode ser usada para pesquisar todos os Teams dados por meio de recursos avançados de filtragem. Os dados resultantes podem ser exportados para um contêiner específico para suporte a conformidade e litígio. Isso pode ser feito com ou sem um caso do eDiscovery. Isso permite que os administradores de conformidade reúnam Teams dados em todos os usuários, revisem e exportem-os para processamento posterior. Consulte a [Pesquisa](/microsoft-365/compliance/content-search) de Conteúdo para saber mais sobre como conduzir uma pesquisa de conteúdo de conformidade para Microsoft Teams e outros Microsoft 365 ou Office 365 conteúdo no Centro de conformidade do Microsoft 365.

> [!TIP]
> Usando a pesquisa de conteúdo, você pode filtrar para Microsoft Teams somente conteúdo, como Chat e Mensagens de Canal, Reuniões e Chamadas, se necessário.

Se você quiser mais informações Teams específicas sobre como configurar a pesquisa de conteúdo, revise a pesquisa de [conteúdo em Microsoft Teams](content-search.md).

### <a name="auditing-and-reporting"></a>Auditoria e relatórios

A pesquisa de log de auditoria conecta-se ao Centro de conformidade do Microsoft 365 e oferece a você a capacidade de definir alertas, bem como relatar eventos de auditoria, permitindo a exportação de conjuntos de eventos específicos ou genéricos de carga de trabalho para uso do administrador e investigação em uma linha do tempo de auditoria ilimitada. Você pode configurar alertas para todos os dados de log de auditoria no Centro de conformidade do Microsoft 365 e filtrar e exportar esses dados para análise posterior. Consulte Pesquisar [o log de auditoria](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) para saber mais sobre como conduzir uma pesquisa de log de auditoria para Microsoft 365 ou Office 365. Para saber mais sobre como pesquisar Microsoft Teams eventos no Centro de conformidade do Microsoft 365, também temos a auditoria Ativar em Teams [para](audit-log-events.md) você analisar.

## <a name="customer-key"></a>Chave do Cliente

Microsoft 365 oferece uma camada adicional de criptografia em cima da criptografia de serviço para seu conteúdo. Usando chaves fornecidas, a Chave do Cliente criptografa vários tipos diferentes de dados Microsoft Teams. Usando a Chave do Cliente no nível do aplicativo, a Chave do Cliente criptografa Teams arquivos armazenados no SharePoint Online. Para obter informações, consulte [Service encryption with Customer Key](/microsoft-365/compliance/customer-key-overview). 

Usando a Chave do Cliente no nível do locatário, a Chave do Cliente criptografa:
- Teams de chat (chats 1:1, chats de grupo, chats de reunião e conversas de canal)
- Teams de mídia (imagens, trechos de código, vídeos e imagens wiki)
- Teams de chamada e reuniões armazenadas no Teams armazenamento
- Teams de chat
- Teams sugestões de chat por Cortana
- Teams de status Para obter mais informações, consulte [Overview of Customer Key for Microsoft 365](/microsoft-365/compliance/customer-key-tenant-level) in the tenant level and read the Microsoft Teams blog that covers Customer Key support for Microsoft Teams now in Public [Preview](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893). Para obter informações sobre Proteção de Informações da Microsoft que incluíam a Chave do Cliente no nível do locatário, leia Anunciando novos recursos Proteção de Informações da Microsoft para saber e proteger [seus dados confidenciais.](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)

## <a name="privacy"></a>Privacidade

Na Microsoft, proteger seus dados é nossa prioridade mais alta. Para saber mais sobre nossas práticas de privacidade, leia:  

- [Privacidade na Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Nosso compromisso com privacidade e segurança no Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Para profissionais de TI: privacidade e segurança no Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Arquitetura de Proteção de Informações

A figura a seguir indica o fluxo de ingestão de Teams dados para Exchange e SharePoint para Teams arquivos e mensagens.

> [!div class="mx-imgBorder"]
> ![Diagrama do fluxo de trabalho dos dados do Microsoft Teams para o Exchange e o SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

A figura a seguir indica o fluxo de ingestão de Teams Reuniões e a chamada de dados para Exchange.

> [!div class="mx-imgBorder"]
> ![Diagrama do fluxo de trabalho de Teams reuniões e de chamada de dados para Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Pode haver até 24 horas de atraso para descobrir Teams conteúdo.

## <a name="licensing"></a>Licenciamento

Quando se trata de recursos de proteção de informações, Microsoft 365 assinaturas, Office 365 assinaturas e as licenças autônomas associadas determinarão o conjunto de recursos disponível.

Para obter informações sobre como determinar as necessidades de licenciamento para implementar recursos de segurança e conformidade, revise os requisitos de licenciamento [para](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) recursos de segurança e conformidade.

> [!NOTE]
> A Pesquisa de Conteúdo e a Descoberta De Conteúdo não precisam ser habilitadas no Centro de Conformidade & segurança para funcionar.

## <a name="location-of-data-in-teams"></a>Localização dos dados no Microsoft Teams

No Teams, os dados são armazenados na região geográfica associada à sua organização do Microsoft 365 ou do Office 365. Para ver quais regiões têm suporte no momento, consulte [Local dos dados em Microsoft Teams](location-of-data-in-teams.md).

Se você precisar ver qual região abriga dados para seu locatário, vá para [o](https://portal.office.com/adminportal/home)perfil Centro de administração do Microsoft 365  >  **Configurações**  >  **Organização.** Role para baixo até **Localização de dados**.

> [!div class="mx-imgBorder"]
> ![Captura de tela da tabela De localização de dados, incluindo Teams no centro de administração.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Padrões de conformidade

Teams usa os seguintes padrões: [ISO 27001](/microsoft-365/compliance/offering-iso-27001), [ISO 27018](/microsoft-365/compliance/offering-iso-27018), [SSAE18 SOC 1 e SOC 2](/microsoft-365/compliance/offering-soc), [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech)e [EUMC (EUMC).](/microsoft-365/compliance/offering-eu-model-clauses) Dentro da estrutura de conformidade da Microsoft, a Microsoft classifica Microsoft 365 e Office 365 aplicativos e serviços em quatro categorias. Cada categoria é definida por compromissos de conformidade específicos que devem ser atendidos para que um serviço Microsoft 365 ou Office 365 ou um serviço da Microsoft relacionado seja listado nessa categoria.

Os detalhes podem ser encontrados nos Recursos [de Proteção de Dados](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides). O Microsoft Teams também dá suporte à conformidade com o Cloud Security Alliance.

## <a name="related-topics"></a>Tópicos relacionados

[Microsoft 365 Segurança](/microsoft-365/security/)

[Microsoft 365 Conformidade](/microsoft-365/compliance/)

[Ofertas de conformidade da Microsoft](/microsoft-365/compliance/offering-home)
