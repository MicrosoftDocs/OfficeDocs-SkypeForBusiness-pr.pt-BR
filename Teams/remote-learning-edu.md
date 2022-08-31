---
title: Introdução ao Microsoft Teams para aprendizado remoto
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith, lakuan
description: Guia de inicialização de aprendizado remoto do Microsoft Teams para EDU.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 231007549102b8cddc02a0d2a5d29266662b4b2f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466019"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Introdução ao Microsoft Teams para aprendizado remoto

Este artigo aborda as etapas de administração de TI para configurar sua instituição educacional para aprendizado remoto usando o Microsoft Teams.

No Teams, **os educadores** podem:

- Converse rapidamente com os alunos.
- Compartilhe arquivos e sites.
- Criar Blocos de Anotações de Classe do OneNote.
  - Organizar lições interativas.
  - Forneça comentários eficazes e em tempo há tempos.
- Distribuir e classificar tarefas.
- Compartilhe material instrucional em Comunidades de Aprendizagem Profissional.

**Os administradores de educação e a equipe** podem:

- Mantenha-se atualizado sobre eventos.
- Colabore usando equipes de equipe para comunicados e conversas tópicos.

# <a name="accounts--licenses"></a>[Contas & licenças](#tab/accounts)

## <a name="user-accounts-licenses-and-identity-security"></a>Contas de usuário, licenças e segurança de identidade

O Teams usa o Microsoft 365 para autenticar usuários e fornecer serviços. Todos os usuários devem ter identidades do Microsoft 365 estabelecidas para facilitar a colaboração.

Se as identidades de usuário ainda não existirem, siga este processo para estabeleça-as:

1. [Criar usuários usando o School Data Sync](/microsoft-365/education/deploy/school-data-sync).
2. [Atribuir licenças aos usuários](teams-edu-licensing.md).
3. [Criar grupos do Microsoft 365](Office-365-groups.md).
4. [Configure o Exchange](Exchange-Teams-interact.md).
5. [Configurar o SharePoint e o OneDrive](SharePoint-OneDrive-interact.md).
6. [Configure os usuários que têm o email do Google](/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

O Microsoft Teams está incluído em todos os planos do Microsoft 365, incluindo o plano gratuito de educação A1.

Para obter diretrizes sobre como implantar o Microsoft 365 e configurar o Teams, confira Criar [seu locatário do Microsoft 365](/microsoft-365/education/deploy/create-your-office-365-tenant).

# <a name="set-up-teams"></a>[Configurar o Teams](#tab/setup)

## <a name="easily-set-up-teams"></a>Configure o Teams facilmente

Aqui estão as duas coisas que você precisa fazer para começar a trabalhar com o Teams:

### <a name="1-allow-users-to-create-teams"></a>1. Permitir que os usuários criem equipes

**Por padrão, todos podem criar grupos do Microsoft 365** e o Teams, mas essa capacidade nem sempre pode ser apropriada.

Por exemplo, algumas escolas podem querer impedir que os alunos criem o Teams sem supervisão. A criação de grupos e equipes do Microsoft 365 pode ser [restrita a determinados grupos de segurança](/microsoft-365/admin/create-groups/manage-creation-of-groups).

Para instituições de ensino superior, recomendamos permitir que todos, incluindo alunos, criem equipes para aulas, pesquisas, projetos em grupo e grupos de estudo.

Para obter um passo a passo de como criar o Teams, consulte [Criar uma equipe de classe no Microsoft Teams](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).

### <a name="2-configure-user-experiences-using-policies"></a>2. Configurar experiências de usuário usando políticas

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Confira Como [manter os alunos seguros no Teams para o aprendizado à distância](https://support.office.com/article/f00fa399-0473-4d31-ab72-644c137e11c8).
>
> Se você quiser exibir nossas recomendações de política EDU, consulte políticas [do Teams e pacotes de políticas para Educação](policy-packages-edu.md).

As políticas do Teams controlam os recursos disponíveis para usuários ou grupos específicos. As políticas podem definir quem deve ter permissão para usar chat privado, chamada privada, agendamento de reunião, tipos de conteúdo que podem ser compartilhados e muito mais.

**Equipes de ensino superior, educadores e alunos** podem usar as políticas padrão (globais). Você pode ajustar as políticas para adicionar mais funcionalidades ao Teams, incluindo recursos [de tradução](messaging-policies-in-teams.md#messaging-policy-settings) e [transcrição automática de reunião](meetings-policies-recording-and-transcription.md#transcription).

**Os alunos do ensino fundamental e médio** podem precisar de recursos restritos. É recomendável que as alterações na política do aluno sejam feitas na política "Global (padrão em toda a organização)".

**Os professores e funcionários** da escola primária e secundária devem receber políticas que concedam recursos importantes, como permitir chat privado e agendamento de reuniões. [Atribua essas políticas em massa para sua equipe e educadores](batch-group-policy-assignment-edu.md).

> [!IMPORTANT]
> Para políticas de reunião atribuídas a qualquer usuário, recomendamos definir  a configuração Admitir automaticamente as pessoas como **Todos em sua organização**. Isso garantirá que os usuários não autenticados sejam admitidos no lobby antes que possam ingressar em reuniões do Teams.
>
> Para mais informações, confira [Gerenciar políticas de reunião no Microsoft Teams](meeting-policies-participants-and-guests.md#automatically-admit-people).

# <a name="class-teams"></a>[Equipes de classe](#tab/class-teams)

## <a name="create-class-teams-for-secure-classroom-use"></a>Criar equipes de classe para uso seguro na sala de aula

O Microsoft Teams para Educação oferece [tipos de equipe específicos](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) para uso educacional. O[ Tipo de equipe de classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) foi projetado para uso em sala de aula e vem com recursos específicos que oferecem suporte às necessidades de sala de aula, incluindo:

- Atribuições.
- Notas.
- Bloco de anotações de sala de aula do OneNote.
- [Pasta Materiais de](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  Classe para proteger conteúdo somente leitura para alunos.
- O [Insights](./class-insights.md) fornece dados em tempo real sobre o compromisso, as atribuições e o bem-estar dos alunos em cada sala de aula.
- [Acesso antecipado ao educador](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) para configurar a classe antes que os alunos sejam adicionados.
- A capacidade de ativar mudo de alunos com interrupção e outras permissões especiais.

As equipes de classe podem ser criadas por meio de:

- [School Data Sync (SDS)](#automatic-team-creation-using-sds).
- [Criação orientada por educadores usando grupos de classes do Microsoft 365](#educator-led-team-creation-from-microsoft-365-class-groups).
- [Scripts do PowerShell usando APIs do Graph](#powershell-script-using-graph-apis).
- [Criação manual de equipe](#manual-team-creation).

Vamos percorrer várias opções para ajudá-lo a escolher o caminho de implantação correto que melhor atende às suas necessidades.

### <a name="automatic-team-creation-using-sds"></a>Criação automática de equipe usando SDS

[O SDS (School Data Sync)](/SchoolDataSync) lê os dados do sistema de registro de uma instituição, como um Sistema de Informações do Aluno (SIS) ou LMS (Sistema de Gerenciamento de Aprendizagem).

O SDS pode importar dados de qualquer sistema de registro e tem conectores internos para muitos [fornecedores do SIS](/schooldatasync/frequently-asked-questions#what-sismis-vendors-does-school-data-sync-support).  

#### <a name="benefits-of-sds"></a>Benefícios do SDS

- Cria automaticamente usuários e aplica licenças.
- Cria e mantém automaticamente as equipes de classe.
- Sincroniza com o SIS/LMS para manter as alterações de associação do aluno.
- [Permite que os educadores preparem as aulas antes de adicionar os alunos](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).
- Pode criar grupos de segurança automaticamente.
- Cria Unidades Administrativas para delegação administrativa com escopo.
- [Permite a redefinição de senha do educador](/schooldatasync/how-to-enable-teacher-password-reset).
- Tem recursos de limpeza internos para renomear e arquivar grupos e equipes.
- [Sincroniza notas do Teams com o SIS](/schooldatasync/grade-sync).
- [Protege os dados pessoais dos alunos](/schooldatasync/protecting-student-personal-data).
- Rastreia e gerencia o consentimento do guardião.
- Fornece melhores Insights para Educação dados.

#### <a name="considerations-for-sds"></a>Considerações sobre o SDS

O SDS cria equipes em duas etapas:

1. O SDS cria um grupo do Microsoft 365 no Azure Active Directory (Azure AD).
2. O SDS transforma automaticamente esse grupo em uma equipe.

A segunda etapa da criação de equipes é opcional no SDS. Um administrador pode não desejar criar equipes automaticamente dependendo do tempo de implantação e o número de equipes não usadas que possam resultar. Em vez disso, consulte [o método de criação de equipe ministrado por educadores](#educator-led-team-creation-from-microsoft-365-class-groups).  

#### <a name="get-started-with-sds"></a>Introdução ao SDS

Para começar, acesse o [SDS (School Data Sync)](/SchoolDataSync) e entre em contato para [https://aka.ms/sdssupport](https://aka.ms/sdssupport) obter assistência de implantação gratuita.  

### <a name="educator-led-team-creation-from-microsoft-365-class-groups"></a>Criação de equipes orientadas por educadores de grupos de classe do Microsoft 365

A criação de equipes orientadas por educadores facilita a criação das classes necessárias para os educadores.  

Essa abordagem permite que você use o SDS para criar grupos para cada classe (recomendado) [ou use API do Graph](/graph/api/educationroot-post-classes) para criar por conta própria.

Depois que os grupos de classe são preparados, os educadores podem converter seus grupos em equipes:

1. Selecione a guia Equipes no Teams.
2. Na parte superior do cliente, selecione o **ícone de classes sugeridas** .

#### <a name="benefits-of-educator-led-team-creation"></a>Benefícios da criação de equipes orientadas por educadores

- As aulas são preparadas e sugeridas, mas não criadas, a menos que o educador pretenda usá-las.
- Para instituições com mais de 500.000 equipes, esse método reduz o número de equipes desnecessárias.
- [Benefícios do SDS](#benefits-of-sds).
- API do Graph benefícios.
  - Fornece aos educadores controle para quais classes são criadas.
  - Não requer integração com o SDS.

#### <a name="considerations-for-educator-led-team-creation"></a>Considerações sobre a criação de equipes orientadas por educadores

- Não totalmente automatizado e requer algumas ações dos educadores.
- Educadores que não têm permissão para criar equipes ainda podem [criar equipes de grupos existentes](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).
- API do Graph requer um alto nível de experiência técnica, tempo para criar e executar o script e tempo para corrigir problemas.

#### <a name="get-started-with-educator-led-team-creation"></a>Introdução à criação de equipes orientadas por educadores

Para começar a usar o método SDS, acesse o [SDS (School Data Sync)](/SchoolDataSync) [https://aka.ms/sdssupport](https://aka.ms/sdssupport) e entre em contato para obter assistência de implantação gratuita.

- Você precisará desativar a alternância de criação automática de equipe em seu perfil do SDS.
- Você pode usar uma combinação de criação automática e de equipe orientada por educadores para equipes de classe usando dois perfis SDS.

Para usar o método de API do Graph, confira [API do Graph](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-1.0&preserve-view=true) e [Criar uma equipe de classe](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true).  

### <a name="powershell-script-using-graph-apis"></a>Script do PowerShell usando APIs do Graph

Com o PowerShell, você pode escrever um script para criar equipes e canais e definir configurações automaticamente.

Esse método exige que o administrador [primeiro crie o grupo, adicione educadores e alunos e, em seguida, crie a equipe](/graph/teams-create-group-and-team).

Você também pode usar o [Microsoft API do Graph para criar, configurar, clonar e arquivar equipes](/graph/api/resources/teams-api-overview).

#### <a name="benefits-of-powershell-scripts"></a>Benefícios dos scripts do PowerShell

- Dá aos administradores de TI controle sobre a criação de classe.
- Opção para criar equipes de acesso antecipado aos educadores ou acesso imediato às equipes para o aluno.
- [Sincroniza as alterações de associação do aluno Azure AD grupo](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

#### <a name="considerations-for-powershell-scripts"></a>Considerações sobre scripts do PowerShell

- Exige um alto nível de experiência técnica e tempo para criar e executar o script e corrigir os problemas na criação de grupos de classe.
- Sem tratamento de erros internos ou lógica de repetição.
- As alterações de associação não são sincronizadas com o SIS.

> [!NOTE]
> As equipes de classe exigem associação a um grupo oculto, para que somente os professores e alunos dentro da classe possam ver os membros dessa classe. Para criar um grupo de classes do Microsoft 365, consulte [Criar uma equipe de classe](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) para atender aos requisitos de privacidade.

### <a name="manual-team-creation"></a>Criação da equipe manualmente

Os usuários podem personalizar a experiência do Teams tendo a capacidade de criar suas próprias equipes.

Dependendo das permissões de um usuário, ele pode:

- [Configure suas próprias equipes e convide usuários, incluindo alunos](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch).
- [Adicione usuários manualmente à equipe](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954).
- [Compartilhe um código de junção](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).
- [Compartilhe um link para a equipe](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

É melhor que os educadores adicionem seus alunos à equipe para garantir que os alunos tenham acesso e sejam notificados de que foram adicionados.

#### <a name="benefits-of-manual-team-creation"></a>Benefícios da criação manual de equipe

- Dá aos educadores controle total da criação de classes.
- As equipes de classe são criadas imediatamente.

#### <a name="considerations-for-manual-team-creation"></a>Considerações sobre a criação manual de equipe

- Exige ações e horas do educador.
- A associação de alunos não é sincronizada com o SIS e requer gerenciamento manual.
- Os alunos terão acesso imediato às equipes de classe.

### <a name="recommended-best-practices"></a>Práticas recomendadas

- Implante antecipadamente para garantir que tudo esteja funcionando de maneira confiável e pronta para o primeiro dia de escola.

- Para problemas com a criação automática de equipe do SDS, os educadores podem usar o método de criação de equipe ministrado [por](#educator-led-team-creation-from-microsoft-365-class-groups) educadores para tentar novamente. [A criação manual de](#manual-team-creation) equipe é outra solução, mas as classes não sincronizam com o SIS.

- O limite da equipe de locatários é de 500.000 equipes. Portanto, os administradores devem reduzir o número de equipes não utilizadas para evitar atingir esses limites. Para obter mais informações, [consulte Limites e especificações do Microsoft Teams](limits-specifications-teams.md).  

# <a name="educator-early-access"></a>[Acesso antecipado do educador](#tab/early-access)

## <a name="early-access-to-class-teams"></a>Acesso antecipado a equipes de classe

O Early Access Class Teams permite que os educadores acessem suas equipes de classe antes que seus alunos possam exibi-lo. Os educadores terão tempo para configurar, adicionar arquivos e se organizar antes de conceder acesso aos alunos.

Quando eles estiverem prontos para que os alunos acessem a equipe, eles poderão [ativar suas aulas](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).

### <a name="how-do-i-create-class-teams-that-allow-educators-early-access-to-set-up-a-team-before-admitting-students"></a>Como criar equipes de classe que permitem aos educadores acesso antecipado a configurar uma equipe antes da admissão de estudantes?

As equipes criadas a partir de grupos (por meio de SDS, ministradas por educadores ou API do Graph) criam automaticamente as equipes de acesso antecipado por padrão.

Para criar sua própria equipe de acesso inicial usando a API do Graph, será necessário [criar uma classe](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) e [criar a equipe a partir de um grupo](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

### <a name="how-do-i-check-if-a-class-is-activated"></a>Como verificar se uma classe está ativada?

No tipo [de recurso de](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true) equipe, exiba a [propriedade isMembershipLimitedToOwners](/graph/api/resources/team?view=graph-rest-beta#properties&preserve-view=true) para ver se uma classe está ativada.

Use o [Obter API da Equipe](/graph/api/team-get?tabs=http&view=graph-rest-beta&preserve-view=true) para consultar a ```isMembershipLimitedToOwners``` propriedade de uma classe específica. Se a equipe estiver ativada, ela retornará um valor falso. Se a equipe não tiver sido ativada, ela retornará um valor verdadeiro.

### <a name="how-do-i-activate-a-class-for-an-educator"></a>Como ativar uma classe para um educador?

Use a [API atualizar equipe](/graph/api/team-update?tabs=http&view=graph-rest-beta&preserve-view=true) e defina a ```isMembershipLimitedToOwners``` propriedade como false para ativar a equipe em nome do seu educador. Depois que uma equipe é ativada, ela não pode ser revertida.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Criar as equipes de funcionários para comunicação e colaboração dos funcionários

[As equipes de](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) tipo de equipe são para administradores de educação e funcionários compartilharem informações e trabalharem juntos em iniciativas de todo o instituto.

Os administradores de educação podem adicionar funcionários à equipe com o assistente de criação de [equipe,](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9) adicionando membros após a criação da equipe ou compartilhando um código de ingresso ou [um link para a equipe](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

# <a name="meeting-scenarios"></a>[Cenários de reunião](#tab/scenarios)

## <a name="teams-meeting-scenarios"></a>Cenários de reuniões no Teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Reuniões colaborativas para classes virtuais

[As reuniões do Microsoft Teams](./tutorial-meetings-in-teams.yml) oferecem suporte para até 250 participantes simultâneos, incluindo a capacidade de ter áudio, vídeo, [compartilhamento de conteúdo](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), quadros de comunicações e anotações compartilhadas.

As reuniões podem ser:

- [Agendado no cliente do Teams](./tutorial-meetings-in-teams.yml).
- Gravado e salvo para que os participantes revisem mais tarde.
- [Transcrita para localizar facilmente o conteúdo](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308).
- Acessado usando um laptop ou celular webcam, microfone e alto-falante.
- [Otimizado para dispositivos específicos](https://products.office.com/microsoft-teams/across-devices/devices).
- Finalizado para todos os participantes para garantir que os alunos não estão em uma reunião não supervisionada.

### <a name="districtuniversity-events-or-updates"></a>Atualizações ou eventos da escola/universidade

Algumas reuniões têm um grande público-alvo e necessidades de produção extras. Essas reuniões costumam ter apresentadores, produtores e moderadores de P e R definidos.

O Microsoft Teams é compatível com essas sessões usando os [Eventos ao vivo do Teams](teams-live-events/what-are-teams-live-events.md).

Eventos ao vivo podem ser usados para cenários, como:

- Atualizações em todo o distrito ou universidade.
- Endereços de liderança.
- Instruções para classes grandes ou grupos de alunos.
- Estendendo-se à sua comunidade.

Saiba mais sobre como realizar sessões ao vivo em:

- [Planeje e agende um evento ao vivo](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).
- [Produza um evento ao vivo](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb).
- [Participe de um evento ao vivo](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac).
- [Moderando um Q&A](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

# <a name="resources"></a>[Recursos](#tab/resources)

## <a name="support-resources"></a>Recursos de suporte

Para obter uma visão geral genérica da transição para o aprendizado remoto, [comece aqui](https://www.microsoft.com/education/remote-learning)

Se você for um administrador de TI, educador, aluno ou responsável, esses recursos poderão ajudá-lo a usar o Teams:

- **Administradores de TI**
  - [Recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).
  - [Baixe e distribua clientes do Teams](get-clients.md).
  - [Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams).
  - [Teams para Infraestrutura de Área de Trabalho Virtualizada](./teams-for-vdi.md).
  - [Monitorar e gerenciar a qualidade da chamada](monitor-call-quality-qos.md).
  - [Verifique a integridade do serviço para o Teams](service-health.md).
  - [Otimize o tráfego do Microsoft 365 para a equipe remota](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).
  - [Contatos de suporte do Teams](/microsoft-365/admin/contact-support-for-business-products).
  - [Teams para Educação webinars](https://aka.ms/TeamsEDUWebinars).

- **Educadores**
  - [Central de ajuda para educadores](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).
  - [Ajuda de aprendizado remoto](https://aka.ms/RemoteLearningHelp).
  - [Baixe o Teams](get-clients.md).
  - [Teams para Educação webinars](https://aka.ms/TeamsEDUWebinars).
  - [Curso online para educadores que usam o Teams](https://education.microsoft.com/course/9c9f5c11/overview).
  - [Curso online para criar Ambientes de Aprendizagem Colaborativa com o Teams](https://education.microsoft.com/course/b1e15cfc/overview).
  - [Arquivo um tíquete de suporte](https://www.microsoft.com/microsoft-teams/download-app).

- **Estudantes**
  - [Central de ajuda para alunos](https://support.office.com/article/student-help-center-395ab230-55bf-44c6-b265-e832d729b694).
  - [Ajuda de aprendizado remoto](https://aka.ms/RemoteLearningHelp).
  - [Baixe o Teams](https://www.microsoft.com/microsoft-teams/download-app).

- **Guardiões**
  - [Ajuda de aprendizado remoto](https://aka.ms/RemoteLearningHelp).
  - [Baixe o Teams](https://www.microsoft.com/microsoft-teams/download-app).

---
