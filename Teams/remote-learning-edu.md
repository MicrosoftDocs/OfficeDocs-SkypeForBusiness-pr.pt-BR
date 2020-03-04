---
title: Recursos do Microsoft Teams para administradores de Educação
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: karsmith
ms.topic: reference
ms.service: msteams
audience: admin
description: Diretrizes de inicialização do aprendizado remoto para o Microsoft Teams para EDU.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87d9e36578227c8f27acfdfd07abfa0cadbe69b7
ms.sourcegitcommit: f23c428043bb0b37c9a8600e64691bc2a1f2e874
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2020
ms.locfileid: "42403830"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Comece a usar o Microsoft Teams para aprendizagem remota

O Microsoft Teams é uma plataforma que reúne conversas, conteúdo, atribuições e aplicativos juntos em um só lugar. Crie salas de aula colaborativas, conecte-se a comunidades de aprendizagem profissional e conecte-se com colegas, tudo isso a partir de uma única experiência.

Use as práticas recomendadas neste artigo para começar a usar o Microsoft Teams para suas necessidades educacionais para habilitar os recursos de aprendizagem remota. O Microsoft Teams pode ser usado para permitir a colaboração de classe envolver alunos em conversas, fornecer uma plataforma de reunião virtual e distribuir tarefas. Administradores escolares e funcionários podem ficar atualizados e colaborar usando o Microsoft Teams para anúncios e Topical conversas. Educadores podem compartilhar materiais de ensino usando comunidades de aprendizagem profissional.

O Microsoft Teams tem [clientes](get-clients.md) disponíveis para área de trabalho (Windows, Mac e Linux), Web e Mobile (Android e Ios) para garantir que todos os seus funcionários e alunos possam permanecer conectados.

Saiba mais sobre os cenários de uso do Microsoft Teams na [série Teams for Education webinar](https://aka.ms/TeamsEDUWebinars).

## <a name="user-accounts-licenses-and-identity-security"></a>Contas de usuário, licenças e segurança de identidade

O Microsoft Teams aproveita os recursos do Microsoft 365 para autenticar usuários e fornecer serviços. Funcionários, instrutores e alunos devem ter identidades estabelecidas para facilitar a colaboração. Se as identidades ainda não existirem, siga este processo para estabelecer.

As [licenças do teams precisam ser habilitadas para os usuários antes de](user-access.md) poderem começar a usar os recursos do teams. O Microsoft Teams depende de recursos adicionais do Microsoft 365, como [grupos do Office 365](Office-365-groups.md), [Exchange](Exchange-Teams-interact.md), [SharePoint e onedrive](SharePoint-OneDrive-interact.md) , para permitir cenários de colaboração. Os usuários recebem a melhor experiência de equipe se todos esses serviços também estiverem habilitados. O Microsoft [Teams é compatível com os usuários que têm emails hospedados pelo Google](https://docs.microsoft.com/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

## <a name="easily-set-up-microsoft-teams"></a>Configurar facilmente o Microsoft Teams

Estas são as duas coisas que você precisa fazer para se familiarizar com o Microsoft Teams:

### <a name="1-allow-users-to-create-teams"></a>1. permitir que os usuários criem equipes

Alunos e professores obterão o máximo de equipes quando puderem usá-lo com barreiras mínimas e terão a flexibilidade de ajustá-lo às suas necessidades. Uma maneira pela qual os usuários podem personalizar a experiência da equipe é ter a capacidade de criar equipes que atendam às suas necessidades. **Por padrão, todos podem criar grupos e equipes do Office 365**. Há ocasiões em que essa funcionalidade pode não ser apropriada; por exemplo, alguns clientes podem querer impedir que os alunos primários secundários criem equipes. Se necessário, o grupo do Office 365 e a criação de equipes podem ser [restritos a certos grupos de segurança](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups) dentro do seu ambiente.

Clientes de ensino mais alto se beneficiam quando você permite que todos, incluindo alunos, criem equipes para classes, pesquisa, projetos de grupo e grupos de estudos. As escolas primárias secundárias podem querer impedir que os alunos criem equipes para garantir que todos os alunos das comunicações dos alunos estejam acontecendo dentro de um fórum que inclua um adulto. Nesse caso, o grupo do Office 365 e a criação da equipe podem ser restritos a todos os educadores e à equipe.

### <a name="2-configure-user-experiences-using-policies"></a>2. configurar experiências do usuário usando políticas

[As políticas do teams](teams-policies.md) fornecem a capacidade de controlar as opções disponíveis para usuários específicos ou grupos de usuários. As políticas podem ser aplicadas para definir quem deve ter permissão para usar chats particulares, chamadas privadas, agendamento de reuniões, tipos de conteúdo que podem ser compartilhados e muito mais.

A **equipe de ensino mais alto, educadores e alunos** beneficiam-se dos recursos incluídos com as políticas padrão (global). Algumas configurações de política adicionais podem ser habilitadas para adicionar mais funcionalidade ao Microsoft Teams, incluindo [habilitar recursos de conversão na política de mensagens](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings) e permitir a transcrição automática de reunião na política de reunião.

**Os estudantes primários secundários da escola** podem precisar de recursos restritos fornecidos aos alunos. Políticas definem limites sobre o que os alunos podem fazer. Como a população dos alunos costuma ser o maior conjunto de usuários e muitas vezes recebe as configurações mais restritivas, é recomendável que as alterações na política do aluno sejam feitas nas políticas "global (toda a organização padrão)".

Aqui está um conjunto de configurações comuns de políticas não padrão que seriam atribuídas a estudantes primários secundários a limitar a comunicação não moderada entre alunos:

#### <a name="messaging-policy"></a>Política de mensagens

- Alterar definido como ' Desativado '
- Classificação de conteúdo Giphy definida como ' estrito '
- Traduzir mensagens definidas como ' ativado '
- Enviar mensagens urgentes usando as notificações de prioridade definidas como ' Desativado '
- Remover usuários de chats em grupo definidos como ' Desativado '

#### <a name="meeting-policy"></a>Política de reunião

- Permitir reunião agora em canais definidos como ' Desativado '
- Permitir o suplemento do Outlook definido como ' Desativado '
- Permitir agendamento de reunião de canal definido como ' Desativado '
- Permitir o agendamento de reuniões privadas definido como ' Desativado '
- Permitir reunião agora em reuniões privadas definidas como ' Desativado '

#### <a name="live-events-policy"></a>Política de eventos ao vivo

- Permitir que o agendamento esteja definido como ' Desativado '

#### <a name="calling-policy"></a>Política de chamada

- Fazer chamadas privadas definidas para ' Desativado '

#### <a name="teams-policy"></a>Política de equipe

- Criar canais privados definidos como ' Desativado '

**Professores e professores primários da escola** devem ter políticas atribuídas com essa concessão dos principais recursos que podem ser restritos aos alunos. Crie novas políticas que permitam o agendamento de chat privado e de reuniões (as configurações padrão para uma nova política). [Atribua essas políticas a seus funcionários e educadores por meio da associação a um grupo de segurança](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).

## <a name="start-using-teams"></a>Começar a usar o Teams

### <a name="create-class-teams-for-secure-classroom-use"></a>Criar equipes de classe para uso seguro da sala de aula

O Microsoft Teams for Education oferece [tipos específicos de equipe](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) para uso educacional. O [tipo de equipe de classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) é projetado para salas de aula com recursos específicos, incluindo: atribuições, um bloco de anotações de sala de aula do OneNote, uma [pasta de materiais de classe](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) para a proteção de conteúdo somente leitura para estudantes e a capacidade de ativar a mudo de alunos para interrupções. Há algumas maneiras como as equipes de classe podem ser implantadas:

1. A equipe de [sincronização de dados da escola](https://sds.microsoft.com/) (SDS) pode ser **configurada por ti**, permitindo que equipes de classe sejam criadas para todas as classes baseadas em informações no sistema de informações da escola. Esse processo provisionará equipes para cada seção e manterá as escalas do instrutor e dos alunos em sincronia. [Educadores terão a capacidade de preparar sua equipe](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) antes dos alunos do admitting. Como alternativa, se um professor não usar a equipe, os alunos não serão admitidos na equipe porque o professor nunca clica em "ativar". O SDS dá suporte a mais de 80 diferentes sistemas de informação da escola (sistemas SIS) para importação de dados, e a [equipe de suporte do SDS](https://aka.ms/SDSSupport) está pronta para ajudar você no planejamento e na configuração.
1. **Professores configuram** sua própria equipe de tipos de classe e convidar os alunos. Educadores podem fazer isso por meio [da adição de alunos à equipe](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954), [compartilhamento de um código de junção](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)ou [compartilhamento de um link para a equipe](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Se possível, é melhor ter educadores adicionar seus alunos à equipe para garantir que os alunos tenham acesso e são notificados de que foram adicionados a uma equipe.

Após a configuração da equipe, os proprietários da equipe podem [Personalizar as configurações da equipe](https://support.office.com/article/find-your-class-team-s-settings-in-microsoft-teams-2592d4de-581d-4952-9028-02317880c158) , incluindo adicionar uma [imagem de equipe](https://support.office.com/article/change-your-team-picture-02ea2af6-b49d-4de8-9551-1a5e472993c0), [criar canais](https://support.office.com/article/create-student-project-groups-channels-in-microsoft-teams-f85b3c07-fb87-4b94-883b-9be55f4b1e45?ui=en-US&rs=en-US&ad=US) para entidades de classe ou áreas de colaboração em grupo, [Adicionar um aplicativo](https://support.office.com/article/add-an-app-to-teams-b2217706-f7ed-4e64-8e96-c413afd02f77) como quizlet/Flipgrid/Kahoot à superfície de conteúdo educacional existente e [mencionar a equipe da sua primeira postagem](https://support.office.com/article/using-the-conversation-tab-in-microsoft-teams-53d1c530-3797-4a6f-9892-6760f8763df2) para notificar todas as pessoas e iniciar a conversa.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Criar equipes de equipe para comunicação e colaboração em equipe

As [equipes de tipo de equipe](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) foram projetadas para administradores e funcionários escolares para compartilhar informações facilmente e trabalhar em conjunto em iniciativas de toda a escola, incluindo a criação de comunicados, a configuração de reuniões, o compartilhamento de conteúdo e a disponibilização de aplicativos externos, como o [Planner para o rastreamento de tarefas](https://support.office.com/article/create-a-plan-with-planner-d000976a-7490-4ddf-b9af-09ee764891e2). Os administradores escolares podem adicionar membros da equipe escolar à equipe por meio do assistente de criação de equipe, [adicionar membros após a criação da equipe](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9)ou [compartilhar um código de junção ou um link para a equipe](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). A [criação de canais](https://support.office.com/article/create-a-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525) é uma ótima maneira de organizar a conversa e os arquivos por workstream ou assunto. [O guia de orientação para os proprietários da equipe](https://support.office.com/article/go-to-guide-for-team-owners-75f9669b-bd8f-457d-b60b-ac2ac9c8ead4?ui=en-US&rs=en-US&ad=US) é um excelente lugar para saber mais sobre as obrigações e os recursos do proprietário da equipe.

## <a name="teams-meeting-scenarios"></a>Cenários de reunião do teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Reuniões colaborativas para aulas virtuais

As [reuniões do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams) dão suporte a até 250 participantes simultâneos, incluindo a capacidade de ter áudio, vídeo, [compartilhamento de conteúdo](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), quadros de comunicações e anotações compartilhadas. As reuniões podem ser agendadas dentro do cliente do Microsoft Teams para [reunião em um espaço privado ou em um canal de equipe](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams), para que todos os membros da equipe saibam sobre isso. As reuniões podem ser gravadas e salvas para que os participantes possam revisar mais tarde. Esses registros também podem ser [transcritas para encontrar conteúdo](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308) que foi discutido com facilidade. Uma webcam, microfone e alto-falante móvel de laptop ou celular podem ser usados para reuniões, e você pode obter qualidade de áudio/vídeo Premium de [dispositivos otimizados do Microsoft Teams](https://products.office.com/microsoft-teams/across-devices/devices).

### <a name="districtuniversity-events-or-updates"></a>Eventos de distrito/Universidade ou atualizações

Algumas instruções precisam de grandes audiências e recursos adicionais de produção. Essas reuniões costumavam ter definido os apresentadores, produtores e Q moderado&A. O Microsoft Teams dá suporte a essas sessões usando [eventos dinâmicos do Microsoft Teams](teams-live-events/what-are-teams-live-events.md). Eventos dinâmicos podem ser usados para cenários, como o distrito ou atualizações em toda a Universidade, endereços de liderança e instruções para aulas grandes ou grupos de alunos, ou se estendem para sua comunidade. Saiba mais sobre como conduzir sessões ao vivo em: [planeje e agende um evento ao vivo](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502), [produza um evento ao vivo](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb), [participe de um evento ao vivo](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)e [como moderar um p&a](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

## <a name="recommended-tips--tricks"></a>Dicas recomendadas & truques

Você pode saber mais sobre como o Microsoft Teams é usado em educação em: [Microsoft Teams para educação](https://support.office.com/article/Teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).

> [!NOTE]
> Alguns dos principais recursos do Microsoft Teams não são específicos do Education. Dicas e truques para os recursos principais do teams podem ser encontrados em: [ajuda e aprendizagem do Microsoft Teams](https://support.office.com/teams).

## <a name="adoption-content"></a>Conteúdo de adoção

A Microsoft desenvolveu [conteúdo de adoção](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76) e orientação estratégica para a implantação do Microsoft Teams. O [Guia de adoção do Microsoft Teams](https://teamworktools.azurewebsites.net/tft/index.html) oferece uma boa visão geral do conteúdo disponível, e o [Kit de sucesso do cliente do teams](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) oferece muitos modelos que podem ser usados para conscientização do teams. O centro de professores da Microsoft oferece treinamento específico para educação sobre como o [Microsoft Teams](https://education.microsoft.com/learningPath/18793af1) e [o OneNote](https://education.microsoft.com/learningPath/b6e3b5f2) são usados na sala de aula.

Recursos de adoção adicionais incluem:

- ["Você pode: 90" vídeos de dicas rápidas](https://www.youtube.com/playlist?list=PLiluTszfwwMKx-yVe7ekBX6gsLIHf1Z8k)
- [Playlist de vídeo do Microsoft Teams para educação](https://www.youtube.com/playlist?list=PLiluTszfwwMKicAo6agloFALEB5WvYNYs)
- [BLOG: Veja como essa escola usa o Microsoft Teams para aprendizado à distância](https://www.wellingtoncollege.cn/tianjin-international/teaching-and-learning-update/)

## <a name="support-readiness"></a>Preparação do suporte

Os profissionais de ti e a equipe de suporte podem se familiarizar com a arquitetura do Teams e o uso subjacente dos recursos do Microsoft 365 com os pôsteres da arquitetura de ti da Microsoft Teams e treinamento técnico de administração.

Recursos de suporte adicionais incluem:

- [Solucionar problemas de instalação e atualização do Microsoft Teams](troubleshoot-installation.md)
- [Monitorar e gerenciar a qualidade da chamada](monitor-call-quality-qos.md)
- [Verificar a integridade do serviço para o Teams](service-health.md)
- [Recursos de suporte para o Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Monitorar e gerenciar a qualidade da chamada](monitor-call-quality-qos.md)
- [Verificar a integridade do serviço para o Teams](service-health.md)
- [Recursos de suporte para o Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Central de ajuda do Microsoft Teams](https://support.office.com/en-us/teams)
