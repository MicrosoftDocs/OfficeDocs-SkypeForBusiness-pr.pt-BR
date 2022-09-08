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
description: Saiba como gerenciar atribuições no Centro de administração do Microsoft Teams no Teams para Educação.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91afcd8036cddfae2550aaddad776958ca413a78
ms.sourcegitcommit: 8b33cc2c2e8f43e6ab4b17715d6a42692351ccad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "67624291"
---
# <a name="assignments-in-teams-for-education"></a>Tarefas do Teams for Education

Os recursos Tarefas e Notas no Teams para Educação permitem que os educadores atribuam tarefas, trabalhos ou testes aos seus alunos. Os educadores podem gerenciar cronogramas de tarefas, instruções, adicionar recursos para entregar, classificar com rubricas e muito mais. Eles também podem acompanhar o progresso das aulas e alunos individuais na guia Notas.

[Saiba mais sobre tarefas e notas no Teams para Educação](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Para obter detalhes sobre as atribuições do Teams em diferentes plataformas, consulte [os recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integrações de atribuições no centro de administração do Microsoft Teams

Usando as configurações de administrador no centro de administração do Microsoft Teams, você pode ativar ou desativar recursos para educadores em sua organização e seus alunos. A seguir estão as configurações relacionadas a Atribuições:

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>Resumo semanal de email do guardião

Emails do guardião são enviados todos os finais de semana para pais ou responsáveis. O email contém informações sobre as atribuições da semana anterior e da próxima semana. A Sincronização de Pais e Responsáveis pode ser configurada usando o [School Data Sync](/schooldatasync/parent-contact-sync).

1. Importe informações de contato pai por meio da Sincronização pai e guardião no SDS. Para obter instruções sobre como habilitar a Sincronização pai e guardião, consulte [Habilitando a sincronização pai e guardião](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Ative a Configuração do Guardião no centro de administração do Microsoft Teams, pois a configuração está desativada por padrão. Isso permitirá que os professores enviem um resumo semanal.

   > [!NOTE]
   > Os professores podem recusar o resumo desmarcando a configuração dentro de sua própria equipe de classe pessoal (Configurações de atribuição > **emails pai/guardião**).

Para verificar se os pais receberão o email, os três itens a seguir devem ser verdadeiros:

- Email endereço anexado ao perfil do aluno no SDS e marcado como _Pai_ ou _Guardião_. Para obter detalhes, consulte [o formato de arquivo de sincronização pai e guardião](/schooldatasync/parent-contact-sync-file-format).

- Os alunos pertencem a pelo menos uma classe na qual o email não é desabilitado pelo professor nas configurações [de tarefa](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

- Os emails conterão informações sobre atribuições que têm uma data de conclusão da semana anterior ou na próxima semana.

A configuração padrão para esse recurso é - **Desativado**.

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

O Microsoft MakeCode é uma plataforma de codificação baseada em blocos que dá vida à ciência da computação para todos os alunos.

MakeCode é um produto da Microsoft que está sujeito aos termos de [uso e às](https://go.microsoft.com/fwlink/?LinkID=206977) políticas [de privacidade da](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft.

A configuração padrão para esse recurso é - **Desativado**.

Para habilitar as atribuições do MakeCode no Teams, vá para o Centro de Administração do **Teams**,  navegue até a seção Atribuições e ative a opção de alternância MakeCode **.** Selecione **Salvar**. Aguarde algumas horas para que essas configurações entre em vigor.

Para obter mais informações sobre como esse recurso funciona, assista a esta [demonstração em vídeo](https://makecode.com/blog/teams/teams-assignments).

[Saiba mais sobre o MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin é](https://www.turnitin.com/) um serviço de integridade acadêmica. Esse é um serviço de terceiros que está sujeito a seus próprios termos e política de privacidade. Você é responsável pelo uso de produtos e serviços de terceiros.

A configuração padrão para esse recurso é - **Desativado**.

Para habilitar o Turnitin para sua organização, você precisará de uma assinatura do Turnitin. Em seguida, você pode inserir as seguintes informações, que podem ser encontradas no console de administração do Turnitin:

- **TurnitinApiKey**: é um GUID de 32 caracteres encontrado no console de administração em Integrações.
- **TurnitinApiUrl**: essa é a URL HTTPS do console de administração do Turnitin.

Aqui estão algumas instruções para ajudá-lo a obter essas informações.

O **TurnitinApiUrl** é o endereço de host do console de administração.
Exemplo: `https://your-tenant-name.turnitin.com`

O console de administração é onde você pode criar uma integração e uma chave de API associada à integração.

Selecione **Integrações** no menu lateral e, em seguida, **selecione Adicionar Integração** e dê um nome à integração.

![Captura de tela mostrando a adição de uma nova integração.](./educationImages/Assignments_mopo_turnitin2.png)

O **TurnitinApiKey** será fornecido a você depois que você seguir os prompts.
Copie a chave de API e cole-a no centro de administração do Microsoft Teams.  Essa é a única vez que você pode exibir a chave.

![Captura de tela mostrando a cópia da chave de API.](./educationImages/Assignments_mopo_turnitin3.png)

Ao clicar no **botão Salvar** no centro de administração para essa configuração, aguarde algumas horas para que essas configurações entre em vigor.

## <a name="assignments-data"></a>Dados de atribuições

As tarefas armazenam informações geradas por professores e alunos. Todos os dados são compartilhados entre o professor e o aluno específico para o qual as informações se destinam na aula. Há dois repositórios desses dados, o SharePoint e fora do SharePoint.

>[!NOTE]
>As mesmas regras também se aplicam a integrações internas, como o Progresso da Leitura.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>Dados de atribuições em bibliotecas de documentos do SharePoint

Os arquivos dos alunos associados a um Envio para Tarefa são armazenados em uma biblioteca de documentos (chamada: *Trabalho do Aluno*). Os arquivos associados às Tarefas criadas por professores e acessíveis por Alunos são armazenados em outra biblioteca de documentos ( *chamada: Arquivos* de Classe) no site correspondente do SharePoint da Equipe de Classe. As integrações internas também podem armazenar dados de Atribuições no mesmo site correspondente do SharePoint da Equipe de Classe (chamado: Título das atribuições *+ carimbo de data/hora*).

#### <a name="files-associated-with-the-student"></a>Arquivos associados ao aluno

Os administradores de TI podem usar a ferramenta Pesquisa de Conteúdo para pesquisar arquivos de *alunos (Trabalho* do *Aluno, Arquivos* de Classe ou outros arquivos de integração de terceiros) relacionados a envios de tarefas e arquivos relacionados a tarefas. Por exemplo, um administrador pode pesquisar todos os sites do SharePoint na organização e usar o nome do aluno e o nome da classe ou da tarefa na consulta de pesquisa para localizar dados relevantes para uma DSR (solicitação de entidade de dados).

#### <a name="files-associated-with-the-teacher"></a>Arquivos associados ao professor

Os administradores de TI podem usar a ferramenta Pesquisa de Conteúdo para pesquisar arquivos de *professor (Trabalho* do *Aluno, Arquivos* de Classe ou outros arquivos de integração de terceiros) relacionados a tarefas e arquivos distribuídos aos alunos pelos professores em uma classe em tarefas. Por exemplo, um administrador pode pesquisar todos os sites do SharePoint na organização e usar o nome do professor e o nome da classe ou da tarefa na consulta de pesquisa para localizar dados relevantes para uma DSR.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>Dados de atribuições fora das bibliotecas de documentos do SharePoint

Alguns dados relacionados a Atribuições não são armazenados no site do SharePoint da equipe de classe, o que significa que não é detectável com a Pesquisa de Conteúdo. Isso inclui:

- Notas dos alunos e comentários do professor
- A lista de documentos enviados para uma tarefa por cada aluno
- Detalhes da atribuição, como Data de Conclusão, etc.
- Dados de integração de terceiros, como passagens de progresso de leitura ou dados de pronúncia do aluno

Para esse tipo de dados, um administrador de TI ou proprietário de dados, como um professor, pode ter que entrar na tarefa na equipe de classe para encontrar dados relevantes para uma DSR. O administrador pode adicionar a si mesmo como proprietário à classe e exibir todas as atribuições dessa equipe de classe.

>[!NOTE]
>Se um aluno não fizer mais parte da classe, seus dados ainda poderão estar presentes na classe, pois *não estão mais registrados*. O aluno precisará fornecer ao administrador de locatários a lista de tais classes das quais ele já fez parte.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>Exportar dados de atribuição em massa fora das bibliotecas de documentos do SharePoint

#### <a name="for-a-student"></a>Para um aluno

Para exportar em massa os dados de um único aluno, antes de remover o aluno das classes das quais ele faz parte, [execute o script](/microsoft-365/education/deploy/configure-assignments-for-teams) e forneça o ``userId``. Se o aluno tiver sido removido do site, o administrador poderá adicionar o aluno de volta à classe antes de executar o script ou ``userId`` ``classId`` o administrador poderá fornecer o e o que o aluno já fez parte.

Os dados sobre os envios dos alunos serão exportados.

#### <a name="for-a-teacher"></a>Para um professor

Os dados de tarefa de Exportação em Massa funcionam da mesma maneira para um aluno, mas todos os envios aos qual o professor tem acesso serão exportados.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>Excluir dados de atribuição em massa fora das bibliotecas de documentos do SharePoint

#### <a name="for-a-student"></a>Para um aluno

Para excluir em massa os dados de um único aluno, antes de remover o aluno das classes das quais ele faz parte, [execute o script](/microsoft-365/education/deploy/configure-assignments-for-teams) e forneça o ``userId``. Se o aluno tiver sido removido do site, o administrador poderá adicionar o aluno de volta à classe antes de executar o script ou ``userId`` ``classId`` o administrador poderá fornecer o e o que o aluno já fez parte.

Fornecer um permitirá ``ClassId`` que o administrador exclua apenas informações sobre o aluno de uma classe específica.

#### <a name="for-a-teacher"></a>Para um professor

Como os dados de uma tarefa para um professor são compartilhados entre a classe, não há nenhuma opção de exclusão em massa. Em vez disso, o administrador pode adicionar-se à classe, ir para o aplicativo e excluir a atribuição.

Para obter mais informações, consulte [Configurar atribuições para o Teams](/microsoft-365/education/deploy/configure-assignments-for-teams).

## <a name="removing-assignments-and-grades"></a>Removendo tarefas e notas

Você também pode usar políticas do Teams para remover tarefas e notas para um usuário específico ou para todo o locatário.

Para remover tarefas e notas de um usuário individual, acesse o **Teams Administração Center** e navegue até aplicativos do **Teams > Políticas** de permissão para criar uma nova definição de política de permissão de aplicativo.  Ao criar a nova definição de política, defina a política  de aplicativos da **Microsoft** como Bloquear **aplicativos específicos** e permita que todos os outros e adicione atribuições e notas à lista de **aplicativos** bloqueados. Depois que a nova definição de política for salva, atribua-a aos usuários apropriados.

Para remover Tarefas e Notas de todo o locatário, acesse o **Teams Administração Center**, navegue até aplicativos do **Teams > Gerenciar** **aplicativos** e pesquise e selecione Tarefas e Notas na lista de **aplicativos**. Altere a configuração de status na página de configurações dos aplicativos para _Bloqueado_.

## <a name="assignments-diagnostic-tool-for-users"></a>Ferramenta de diagnóstico de atribuições para usuários

Suporte da Microsoft criou uma ferramenta para coletar dados de diagnóstico para a equipe de engenharia da Microsoft investigar problemas relacionados ao recurso Atribuições.

Essa ferramenta pode ser acessada dentro de Atribuições em qualquer tela em que os usuários experimentarem um problema.

Para efetuar pull da ferramenta de diagnóstico no Teams, os usuários podem:

- **Na área de trabalho e na Web:**
  - Selecione Ctrl+/
- **Em dispositivos móveis:**
  - Toque na tela com dois dedos e gire os dedos 45 graus ou
  - Toque na tela com três dedos por 15 segundos

Depois que a ferramenta de diagnóstico for exibida, os usuários verão uma lista de dados que podem ser necessários para o suporte técnico da Microsoft.

Os dados extraídos podem incluir:

- ID do Grupo
- ID do locatário
- ID da Sessão
- ID da Atribuição
- ID de envio
- ID do Usuário

Esses dados não são enviados automaticamente à Microsoft. Os usuários precisam copiar e colar os dados em um agente de suporte da Microsoft em relação a um tíquete de suporte.

Se um usuário puxar a ferramenta de diagnóstico, então a fechará, nenhum dado será enviado.

Quando os dados são enviados a um agente de suporte da Microsoft, eles são tratados como Dados de Suporte nos contratos de serviço do Microsoft 365 da sua organização.

Para obter instruções sobre como usar essa ferramenta de diagnóstico que você pode compartilhar com educadores e alunos, consulte Obter dados de diagnóstico [para solucionar problemas de tarefas](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e).
