---
title: Recursos do Microsoft Teams para administradores de Educação
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: karsmith
ms.topic: reference
ms.service: msteams
audience: admin
description: Guia de inicialização de aprendizado remoto do Microsoft Teams para EDU.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2455a725822183d3e953993632a634a43002523
ms.sourcegitcommit: 0286eec17b7eea486b857a69fb6c6166ef0799d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2020
ms.locfileid: "42408876"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Introdução ao Microsoft Teams para aprendizado remoto

O Microsoft Teams é uma plataforma que reúne conversas, conteúdo, atribuições e aplicativos em um só lugar. Crie salas de aula colaborativas, conecte-se a comunidades de aprendizagem profissional e com os colegas, tudo em uma só experiência.

Use as práticas recomendadas nesse artigo para começar a usar o Microsoft Teams para suas necessidades educacionais e habilitar os recursos de aprendizado remoto. O Microsoft Teams pode ser usado para habilitar a colaboração de classe estimulando as conversas entre os alunos, fornecendo uma plataforma de reunião virtual e distribuindo atribuições. Os administradores e funcionários da escola podem ficar atualizados e colaborar usando o Teams para anúncios e grupos de conversas. Os professores podem compartilhar materiais de ensino usando as Comunidades de Aprendizagem Profissional.

O Microsoft Teams tem [clientes](get-clients.md) disponíveis para área de trabalho (Windows, Mac e Linux), para Web e para dispositivos móveis (Android e iOS) garantindo que toda a equipe e os alunos possam se conectar.

Saiba mais sobre os cenários de uso do Microsoft Teams na [série de webinar de educação do Teams](https://aka.ms/TeamsEDUWebinars).

## <a name="user-accounts-licenses-and-identity-security"></a>Contas de usuário, licenças e segurança de identidade

O Microsoft Teams utiliza os recursos do Microsoft 365 para autenticar os usuários e fornecer serviços. Os professores, funcionários e alunos devem ter identidades estabelecidas para facilitar a colaboração. Se as identidades ainda não existirem, siga este processo para estabelecê-las.

[As licenças do Teams devem ser habilitadas para os usuários](user-access.md) para que eles possam começar a usar os recursos do Teams. O Teams depende de recursos adicionais do Microsoft 365, como os [grupos do Office 365](Office-365-groups.md), o [Exchange](Exchange-Teams-interact.md), o [SharePoint e o OneDrive](SharePoint-OneDrive-interact.md) para habilitar os cenários de colaboração. Os usuários recebem a melhor experiência do Teams se todos esses serviços também estiverem habilitados. [O Teams têm suporte para usuários com emails hospedados pelo Google](https://docs.microsoft.com/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

## <a name="easily-set-up-microsoft-teams"></a>Configure com facilidade o Microsoft Teams

Estas são as duas coisas que você precisa fazer para começar a trabalhar com o Teams:

### <a name="1-allow-users-to-create-teams"></a>1. Permitir que os usuários criem equipes

Estudantes e professores aproveitarão ao máximo o Teams ao usá-lo com barreiras mínimas e terão a flexibilidade para adaptá-lo às suas necessidades. Uma forma dos usuários personalizarem a experiência do Teams é ter a capacidade de criar equipes que atendem às suas necessidades. **Por padrão, todos podem criar grupos no Teams e no Office 365**. Há momentos em que esse recurso pode não ser apropriado; por exemplo, alguns clientes podem querer impedir que os alunos do ensino fundamental criem grupos no Teams. Se necessário, a criação de equipes e grupos do Office 365 pode ser [restrita a determinados grupos de segurança](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups) em seu ambiente.

Os clientes do ensino superior se beneficiam quando você permite que todos, inclusive estudantes, criem equipes para aulas, pesquisas, projetos e grupos de estudo. As escolas de ensino integral podem impedir a criação no Teams para garantir que todas as comunicações entre alunos ocorram em um fórum que inclua um adulto. Nesse caso, a criação de equipes e grupos do Office 365 pode ser restrita a todos os professores e funcionários.

### <a name="2-configure-user-experiences-using-policies"></a>2. Configurar experiências de usuário usando políticas

[As políticas do Teams](teams-policies.md) oferecem a capacidade de controlar as opções disponíveis para usuários específicos ou grupos de usuários. As políticas podem ser aplicadas para definir quem deve ter permissão para usar o chat privado, chamadas particulares, agendamento de reuniões, tipos de conteúdo que podem ser compartilhados e muito mais.

**A equipe de ensino superior, professores e estudantes** se beneficiam dos recursos incluídos nas políticas padrão (globais). Algumas configurações adicionais de política podem ser habilitadas para adicionar mais funcionalidade ao Microsoft Teams, incluindo o [habilitar recursos de tradução na política de mensagens](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings) e permitir a transcrição automática da reunião na política de reunião.

Talvez seja necessário restringir os recursos fornecidos aos **estudantes de ensino básico e fundamental**. As políticas definem os limites do que os alunos podem fazer. Como a população de alunos geralmente é o maior conjunto de usuários e, muitas vezes, eles recebem as configurações mais restritivas, é recomendável que as alterações na política do aluno sejam feitas nas políticas "Globais (padrão da organização)".

Este é um conjunto de configurações de política comum não padrão que podem ser atribuídas aos estudantes de ensino básico e fundamental a fim de limitar a comunicação sem supervisão entre os alunos:

#### <a name="messaging-policy"></a>Políticas de mensagens

- Mudar a configuração para "desligado"
- Classificação de conteúdo Giphy definido como "estrito"
- Traduzir as mensagens definido como "ligado"
- Enviar mensagens urgentes usando as notificações de prioridade definido como "desligado"
- Remover usuários de conversas de grupo definidas como "desligado"

#### <a name="meeting-policy"></a>Políticas de reunião

- Permitir Reunir agora nos canais definido como "desligado"
- Permitir o suplemento do Outlook definido como "desligado"
- Permitir o agendamento de reunião do canal definido como "desligado"
- Permitir o agendamento de reuniões particulares definido como "desativado"
- Permitir Reunir agora em reuniões particulares definido como "desativado"

#### <a name="live-events-policy"></a>Políticas de eventos ao vivo

- Permitir o agendamento definido como "desligado"

#### <a name="calling-policy"></a>Políticas de chamada

- Fazer chamadas privadas definido como "desligado"

#### <a name="teams-policy"></a>Políticas do Teams

- Criar canais privados definido como "desligado"

**Os professores e funcionários do ensino básico** devem receber políticas que concedam os principais recurso que podem ser restritos aos alunos. Crie novas políticas que permitem o agendamento de reuniões e o chat privado (as configurações padrão para uma nova política). [Atribua essas políticas aos seus funcionários e professores por meio da associação de grupo de segurança](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).

## <a name="start-using-teams"></a>Começar a usar o Teams

### <a name="create-class-teams-for-secure-classroom-use"></a>Criar equipes de classe para uso seguro na sala de aula

O Microsoft Teams para Educação oferece [tipos de equipes específicos](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) para uso educacional. O [Tipo de equipe de classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) foi projetado para as salas de aula com recursos específicos, incluindo: atribuições, um bloco de anotações do OneNote na sala de aula, uma [pasta de materiais da classe](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) para proteger o conteúdo somente leitura para estudantes e a capacidade de ativar o mudo para alunos que atrapalham. Há algumas maneiras de implantar as equipes de classe:

1. O recurso [SDS (School Data Sync)](https://sds.microsoft.com/) pode ser **configurado pela TI**, permitindo que as equipes de classe sejam criadas para todas as classes com base nas informações do sistema de informações da escola. Esse processo provisionará equipes para cada seção e manterá a lista de professores e alunos sincronizada. Os [professores terão a capacidade de preparar suas equipes](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) antes de aceitar os alunos. Como alternativa, se um professor não quiser usar a equipe, os alunos não serão aceitos na equipe porque o professor nunca clicará em "ativar". O SDS é compatível com mais de 80 diferentes sistemas de informações escolares (sistemas SIS) para importação de dados, e a [equipe de suporte do SDS](https://aka.ms/SDSSupport) está pronta para ajudar você no planejamento e configuração.
1. Os **professores configuram** seu próprio tipo de classe da equipe e convidam os alunos. Os Professores podem fazer isso ao [adicionar alunos à equipe](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954), ao [compartilhar um código de ingresso](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f) ou ao [compartilhar um link para a equipe](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Se possível, é melhor que os professores adicionem seus alunos à equipe para garantir que eles tenham acesso e sejam notificados de que foram adicionados a uma equipe.

Após a configuração da equipe, os proprietários da equipe podem [personalizar as configurações da equipe](https://support.office.com/article/find-your-class-team-s-settings-in-microsoft-teams-2592d4de-581d-4952-9028-02317880c158), incluindo adicionar uma [imagem da equipe](https://support.office.com/article/change-your-team-picture-02ea2af6-b49d-4de8-9551-1a5e472993c0), [criar canais](https://support.office.com/article/create-student-project-groups-channels-in-microsoft-teams-f85b3c07-fb87-4b94-883b-9be55f4b1e45?ui=en-US&rs=en-US&ad=US) para assuntos das aulas ou áreas de colaboração em grupo, [adicionar um aplicativo](https://support.office.com/article/add-an-app-to-teams-b2217706-f7ed-4e64-8e96-c413afd02f77) como Quizlet/Flipgrid/Kahoot para exibir o conteúdo educacional existente e [mencionar a equipe na primeira postagem](https://support.office.com/article/using-the-conversation-tab-in-microsoft-teams-53d1c530-3797-4a6f-9892-6760f8763df2) para notificar todos e iniciar a conversa.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Criar a equipes de funcionários para comunicação e colaboração dos funcionários

As [equipes de tipo funcionários](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) foram projetadas para que os administradores e funcionários da escola compartilhem informações e trabalhem em conjunto em iniciativas de toda a escola, incluindo a elaboração de comunicados, marcações de reuniões, compartilhamento de conteúdo e a disponibilização de aplicativos externos, como [Planner para o acompanhamento de tarefas](https://support.office.com/article/create-a-plan-with-planner-d000976a-7490-4ddf-b9af-09ee764891e2). Os administradores da escola podem adicionar membros da equipe escolar à equipe por meio do assistente de criação de equipe, [adicionar membros após a criação da equipe](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9) ou ao [compartilhar um código de ingresso ou um link para a equipe](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). [Criar canais](https://support.office.com/article/create-a-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525) é uma ótima maneira de organizar conversas e arquivos por fluxo de trabalho ou assunto. [O guia de introduções para proprietários de equipes](https://support.office.com/article/go-to-guide-for-team-owners-75f9669b-bd8f-457d-b60b-ac2ac9c8ead4?ui=en-US&rs=en-US&ad=US) é um local excelente para saber mais sobre os recursos e as funções do proprietário da equipe.

## <a name="teams-meeting-scenarios"></a>Cenários de reuniões no Teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Reuniões colaborativas para classes virtuais

[As reuniões do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams) oferecem suporte para até 250 participantes simultâneos, incluindo a capacidade de ter áudio, vídeo, [compartilhamento de conteúdo](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), quadros de comunicações e anotações compartilhadas. As reuniões podem ser agendadas dentro do cliente do Microsoft Teams como [reunião em um espaço particular ou em um canal de equipe](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams), para que todos os membros da equipe saibam sobre ela. As reuniões podem ser gravadas e salvas para que os participantes possam revisá-las posteriormente. Essas gravações também podem ser [transcritas para encontrar com facilidade o conteúdo](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308) que foi discutido. Uma câmera, microfone e alto-falante de laptop ou de telefone celular podem ser usados para as reuniões, e você pode obter a qualidade premium de áudio/vídeo com [dispositivos otimizados para o Microsoft Teams](https://products.office.com/microsoft-teams/across-devices/devices).

### <a name="districtuniversity-events-or-updates"></a>Atualizações ou eventos da escola/universidade

Algumas instruções precisam de públicos maiores e de recursos adicionais de produção. Essas reuniões costumam ter apresentadores, produtores e moderadores de P e R definidos. O Microsoft Teams é compatível com essas sessões usando os [Eventos ao vivo do Teams](teams-live-events/what-are-teams-live-events.md). Os Eventos ao vivos podem ser usados em cenários, como as atualizações em toda a escola ou universidade, discursos da liderança e instruções para grandes classes ou grupos de alunos, ou pela comunidade. Saiba mais sobre como realizar sessões ao vivo em: [planejar e agendar um evento ao vivo](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502), [produzir um evento ao vivo](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb), [participar de um evento ao vivo](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac) e [moderar uma sessão de P e R](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

## <a name="recommended-tips--tricks"></a>Dicas e truques recomendados

Você pode saber mais sobre como o Microsoft Teams é usado na educação em: [Microsoft Teams para Educação](https://support.office.com/article/Teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).

> [!NOTE]
> Alguns dos principais recursos do Microsoft Teams não são específicos para educação. As dicas e truques para os principais recursos do Teams podem ser encontradas em: [Ajuda e aprendizagem do Microsoft Teams](https://support.office.com/teams).

## <a name="adoption-content"></a>Conteúdo de adoção

A Microsoft desenvolveu o [conteúdo de adoção](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76) e o guia de estratégias para a implantação do Microsoft Teams. O [guia de adoção do Microsoft Teams](https://teamworktools.azurewebsites.net/tft/index.html) fornece uma visão geral do conteúdo disponível e o [Kit de Sucesso de Cliente do Teams](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) fornece muitos modelos que podem ser usados para conscientização sobre o Teams. O Centro de Educação da Microsoft oferece treinamento educacional específico sobre como o [Microsoft Teams](https://education.microsoft.com/learningPath/18793af1) e o [OneNote](https://education.microsoft.com/learningPath/b6e3b5f2) são usados na sala de aula.

Os recursos adicionais de adoção incluem:

- ["Você pode em: 90" vídeos de dicas rápidas](https://www.youtube.com/playlist?list=PLiluTszfwwMKx-yVe7ekBX6gsLIHf1Z8k)
- [Lista de reprodução de vídeos do Microsoft Teams para Educação](https://www.youtube.com/playlist?list=PLiluTszfwwMKicAo6agloFALEB5WvYNYs)
- [BLOG: Veja como essa escola usa o Teams para ensino à distância](https://www.wellingtoncollege.cn/tianjin-international/teaching-and-learning-update/)

## <a name="support-readiness"></a>Prontidão de suporte

Os profissionais de TI e a equipe de suporte podem se familiarizar rapidamente com a arquitetura do Teams e o uso subjacente dos recursos do Microsoft 365 com os pôsteres da arquitetura de TI do Microsoft Teams e o treinamento técnico de administrador.

Os recursos de suporte adicionais incluem:

- [Solucionar problemas de instalação e atualização do Microsoft Teams](troubleshoot-installation.md)
- [Monitorar e gerenciar a qualidade da chamada](monitor-call-quality-qos.md)
- [Verificar a integridade do serviço para o Teams](service-health.md)
- [Recursos de suporte para o Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Monitorar e gerenciar a qualidade da chamada](monitor-call-quality-qos.md)
- [Verificar a integridade do serviço para o Teams](service-health.md)
- [Recursos de suporte para o Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Centro de ajuda do Microsoft Teams](https://support.office.com/pt-BR/teams)
