---
title: Tarefas do Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Saiba como gerenciar atribuições no Microsoft Teams de administração no Teams para Educação.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 529240db27824ce8bf872d23636b904198ef7db1
ms.sourcegitcommit: ecc67b7b9378cc72f85517f30c32680045056fda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2022
ms.locfileid: "64504131"
---
# <a name="assignments-in-teams-for-education"></a>Tarefas do Teams for Education

Os recursos Atribuições e Notas no Teams para Educação permitem que os educadores atribuam tarefas, trabalhos ou testes aos alunos. Os educadores podem gerenciar cronogramas de atribuição, instruções, adicionar recursos para a atribuição, notas com rubricas e muito mais. Eles também podem acompanhar o progresso da classe e do aluno individual na guia Notas.

[Saiba mais sobre atribuições e notas no Teams para Educação](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Para obter detalhes Teams atribuições em diferentes plataformas, [consulte Teams recursos por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integrações de atribuições no Microsoft Teams de administração

Usando as configurações de administrador no Microsoft Teams de administração, você pode ativar ou desativar recursos para educadores em sua organização e seus alunos. Veja a seguir as configurações relacionadas a atribuições:

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>Resumo semanal de email do guardião

Emails de tutor são enviados a cada fim de semana para pais ou responsáveis. O email contém informações sobre atribuições da semana anterior e da próxima semana. A Sincronização pai e guardião pode ser configurada usando [School Data Sync](/schooldatasync/parent-contact-sync).

1. Importar informações de contato pai por meio da Sincronização pai e guardião no SDS. Para obter instruções sobre como habilitar a sincronização pai e guardião, consulte [Enableing Parent and Guardian Sync](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. A opção Ativar a Configuração do Guardião no Microsoft Teams de administração, já que a configuração está desabilitada por padrão. Isso permitirá que os professores enviem um resumo semanal.

   > [!NOTE]
   > Os professores podem optar por não participar do resumo desmarcando a configuração dentro de sua própria equipe de classe pessoal (**Atribuição Configurações > Emails pai/tutor**).

Para verificar se os Pais receberão o email, os três itens a seguir devem ser verdadeiros:

- Endereço de email anexado ao perfil do aluno no SDS e marcado como _Pai_ ou _Guardião_. Para obter detalhes, consulte [Parent and Guardian Sync File Format](/schooldatasync/parent-contact-sync-file-format).

- Os alunos pertencem a pelo menos uma classe na qual o email não está desabilitado pelo professor nas configurações [de atribuição](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

- Os emails conterão informações sobre atribuições que tenham uma data de vencimento da semana anterior ou na próxima semana.

A configuração padrão para esse recurso é - **Off**.

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

O Microsoft MakeCode é uma plataforma de codificação baseada em blocos que dá vida à ciência da computação para todos os alunos.

MakeCode é um produto da Microsoft que está sujeito aos termos [de uso e](https://go.microsoft.com/fwlink/?LinkID=206977) políticas [de privacidade da](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft.

A configuração padrão para esse recurso é - **Off**.

Para habilitar as Teams MakeCode, vá para o Centro de Administração Teams, navegue até a seção Atribuições e  ative **a** opção de alternância MakeCode para **Ativado**. Selecione **Salvar**. Permita algumas horas para que essas configurações entre em vigor.

Para obter mais informações sobre como esse recurso funciona, assista a esta [demonstração de vídeo](https://makecode.com/blog/teams/teams-assignments).

[Saiba mais sobre MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin é](https://www.turnitin.com/) um serviço de integridade acadêmica. Esse é um serviço de terceiros que está sujeito aos seus próprios termos e política de privacidade. Você é responsável pelo uso de produtos e serviços de terceiros.

A configuração padrão para esse recurso é - **Off**.

Para habilitar o Turnitin para sua organização, você precisará de uma assinatura turnitin. Em seguida, você pode inserir as seguintes informações, que podem ser encontradas no console de administração turnitin:

- **TurnitinApiKey**: este é um GUID de 32 caracteres encontrado no console de administração em Integrações.
- **TurnitinApiUrl**: esta é a URL HTTPS do console de administração turnitin.

Aqui estão algumas instruções para ajudá-lo a obter essas informações.

**TurnitinApiUrl** é o endereço host do console de administração.
Exemplo: `https://your-tenant-name.turnitin.com`

O console de administrador é onde você pode criar uma integração e uma chave de API associada à integração.

Selecione **Integrações** no menu lateral e selecione **Adicionar Integração** e dê um nome à integração.

![Captura de tela mostrando a adição de uma nova integração.](./educationImages/Assignments_mopo_turnitin2.png)

O **TurnitinApiKey** será dado a você depois de seguir os prompts.
Copie a chave da API e a colar no Microsoft Teams de administração.  Esta é a única hora em que você pode exibir a chave.

![Captura de tela mostrando a cópia da chave da API.](./educationImages/Assignments_mopo_turnitin3.png)

Ao clicar no **botão Salvar** no centro de administração para essa configuração, permita algumas horas para que essas configurações entre em vigor.

## <a name="assignments-data"></a>Dados de atribuições

As atribuições armazenam informações geradas por professores e alunos. Todos os dados são compartilhados entre o professor e o aluno específico para o qual as informações se destinam na aula. Há dois armazenamentos desses dados, SharePoint e fora do SharePoint.

>[!NOTE]
>As mesmas regras também se aplicam a integrações de primeira parte, como o Progresso da Leitura.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>Dados de atribuições em SharePoint de documentos

Os arquivos dos alunos associados a um Envio para Atribuição são armazenados em uma biblioteca de documentos (chamada: *Trabalho do Aluno*). Os arquivos associados a Atribuições que são criados por professores e acessíveis por alunos são armazenados em outra biblioteca de documentos (*denominada: Arquivos* de Classe) no site correspondente de equipe de classe SharePoint site. As integrações de primeira parte também podem armazenar dados de atribuições no mesmo site de equipe de classe correspondente SharePoint site (chamado: Título de atribuições *+ carimbo de hora*).

#### <a name="files-associated-with-the-student"></a>Arquivos associados ao aluno

Os administradores de IT podem usar a ferramenta Pesquisa de Conteúdo para pesquisar arquivos de *alunos (Trabalho* do *Aluno, Arquivos* de Classe ou outros arquivos de integração de terceiros) relacionados a envios de atribuições e arquivos relacionados a atribuições. Por exemplo, um administrador pode pesquisar todos os SharePoint na organização e usar o nome e o nome da classe ou atribuição do aluno na consulta de pesquisa para encontrar dados relevantes para uma solicitação de entidade de dados (DSR).

#### <a name="files-associated-with-the-teacher"></a>Arquivos associados ao professor

Os administradores de IT podem usar a ferramenta Pesquisa de Conteúdo para pesquisar arquivos de *professores (Trabalho* do *Aluno, Arquivos* de Classe ou outros arquivos de integração de 1ª parte) relacionados a atribuições e arquivos distribuídos aos alunos pelos professores em uma aula sobre atribuições. Por exemplo, um administrador pode pesquisar todos os SharePoint na organização e usar o nome e o nome da classe ou atribuição do professor na consulta de pesquisa para encontrar dados relevantes para uma DSR.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>Dados de atribuições fora de SharePoint de documentos

Alguns dados relacionados a Atribuições não são armazenados no site da equipe de classe SharePoint, o que significa que eles não podem ser descobertos com a Pesquisa de Conteúdo. Isso inclui:

- Notas dos alunos e comentários do professor
- A lista de documentos enviados para uma atribuição por cada aluno
- Detalhes da atribuição, como Data de Vencimento, etc.
- Dados de integração de primeira parte, como passagens de progresso de leitura ou dados de pronúncia do aluno

Para esse tipo de dados, um administrador de IT ou proprietário de dados, como um professor, pode ter que entrar na atribuição na equipe de classe para encontrar dados relevantes para uma DSR. O administrador pode adicionar a si mesmo como proprietário à classe e exibir todas as atribuições dessa equipe de classe.

>[!NOTE]
>Se um aluno não faz mais parte da classe, seus dados ainda podem estar presentes na classe como *não estão mais inscritos*. O aluno terá que fornecer ao administrador do locatário a lista de classes das que eles já fizeram parte.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>Exportar dados de atribuição em massa fora de SharePoint de documentos

#### <a name="for-a-student"></a>Para um aluno

Para exportar em massa os dados de um único aluno, antes de remover o aluno das classes das que fazem parte, execute o  [script](/microsoft-365/education/deploy/configure-assignments-for-teams) e forneça o ``userId``. Se o aluno tiver sido removido do site, o administrador poderá adicionar o aluno de volta à classe antes de executar o script, ``userId`` ``classId`` ou o administrador poderá fornecer o e o que o aluno já fez parte.

Os dados sobre os envios de alunos serão exportados.

#### <a name="for-a-teacher"></a>Para um professor

Exportar dados de atribuição em massa funciona da mesma maneira para um aluno, mas todos os envios aos que o professor tem acesso serão exportados.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>Excluir dados de atribuição em massa fora de SharePoint de documentos

#### <a name="for-a-student"></a>Para um aluno

Para excluir em massa os dados de um único aluno, antes de remover o aluno das classes das que fazem parte, execute o [script](/microsoft-365/education/deploy/configure-assignments-for-teams) e forneça o ``userId``. Se o aluno tiver sido removido do site, o administrador poderá adicionar o aluno de volta à classe antes de executar o script, ``userId`` ``classId`` ou o administrador poderá fornecer o e o que o aluno já fez parte.

Fornecer um permitirá ``ClassId`` que o administrador exclua apenas informações sobre o aluno de uma classe específica.

#### <a name="for-a-teacher"></a>Para um professor

Como os dados de uma atribuição para um professor são compartilhados na classe, não há opção de exclusão em massa. Em vez disso, o administrador pode adicionar a si mesmo à classe, ir para o aplicativo e excluir a atribuição.

Para obter mais informações,  [consulteConfigure assignments for Teams](/microsoft-365/education/deploy/configure-assignments-for-teams).

## <a name="removing-assignments-and-grades"></a>Removendo atribuições e notas

Você também pode usar Teams para remover atribuições e notas para um usuário específico ou para todo o locatário.

Para remover atribuições e notas de um usuário individual, vá para o  Centro de Administração Teams e navegue até Teams aplicativos **> Políticas** de permissão para criar uma nova definição de política de permissão de aplicativo.  Ao criar a nova definição de política, desmarque  a política de aplicativos da **Microsoft** como Bloquear **aplicativos específicos** e permita que todos os outros e adicione atribuições à lista de aplicativos bloqueados. Depois que a nova definição de política for salva, atribua-a aos usuários apropriados.

Para remover atribuições e notas de todo o locatário, vá para o Centro de Administração **Teams,** navegue até Teams **aplicativos > Gerenciar** **aplicativos e pesquise** e selecione Atribuições na lista de aplicativos. Altere a configuração de status na página Configurações do aplicativo de atribuição como _Bloqueado_.

## <a name="assignments-diagnostic-tool-for-users"></a>Ferramenta de diagnóstico de atribuições para usuários

O Suporte da Microsoft criou uma ferramenta para coletar dados de diagnóstico para a equipe de engenharia da Microsoft para investigar problemas relacionados ao recurso Assignments.

Essa ferramenta pode ser acessada dentro de Atribuições em qualquer tela que os usuários experimentem um problema.

Para puxar a ferramenta de diagnóstico no Teams, os usuários podem:

- **Na área de trabalho e na Web:**
  - Selecione Ctrl+/
- **Em dispositivos móveis:**
  - Toque na tela com dois dedos e gire os dedos 45 graus ou
  - Toque na tela com três dedos por 15 segundos

Depois que a ferramenta de diagnóstico aparecer, os usuários verão uma lista de dados que podem ser necessários para o suporte técnico da Microsoft.

Os dados coletados podem incluir:

- ID do grupo
- ID do locatário
- ID da sessão
- ID de atribuição
- ID de envio
- ID do Usuário

Esses dados não são enviados automaticamente para a Microsoft. Os usuários precisam copiar e colar os dados a um agente de suporte da Microsoft em relação a um tíquete de suporte.

Se um usuário puxar a ferramenta de diagnóstico, então a fechará, nenhum dado será enviado.

Quando os dados são enviados a um agente de suporte da Microsoft, eles são tratados como Dados de Suporte nos contratos de serviço Microsoft 365 da sua organização.

Para obter instruções sobre como usar essa ferramenta de diagnóstico que você pode compartilhar com educadores e alunos, consulte Obter dados de diagnóstico [para solucionar problemas de atribuições](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e).
