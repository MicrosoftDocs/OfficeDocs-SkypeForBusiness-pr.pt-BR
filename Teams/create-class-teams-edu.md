---
title: Métodos e práticas recomendadas para a criação de equipes de classe
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: lakuan
description: Saiba mais sobre os métodos e práticas recomendadas para criar equipes de classe para sua escola.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3e8b8e8605b5e4f916389109cb611996aa90a895
ms.sourcegitcommit: 34a30c2c9a8e32bfcb382c3e6e7237f277ec361d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45206758"
---
# <a name="recommended-methods-and-best-practices-for-creating-class-teams"></a>Métodos e práticas recomendadas para a criação de equipes de classe

O Microsoft Teams para Educação oferece   [tipos de equipes específicos](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)  para uso educacional. O[ Tipo de equipe de classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) foi projetado para uso em sala de aula e vem com recursos específicos que oferecem suporte às necessidades de sala de aula, incluindo:  

- Tarefas
- Notas
- Bloco de anotações de classe do OneNote  
- [Pasta de materiais de classe](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  garantindo o conteúdo somente leitura para estudantes
- [Acesso antecipado ao professor](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) para organizar a classe antes que os alunos sejam adicionados 
- A capacidade silenciar alunos bagunceiros e outras permissões especiais.  

Há algumas maneiras de criar equipes de classe, e Teams para Educação possui um conjunto exclusivo de ferramentas de implantação para torná-las o mais fácil possível. Vamos percorrer várias opções para ajudá-lo a escolher o caminho de implantação correto que melhor atende às suas necessidades.  

## <a name="automatic-team-creation-using-sds"></a>Criação automática de equipe usando SDS

**Esse recurso será lançado em breve, no final de julho de 2020.**

A automação da criação de equipe poupa o tempo dos administradores de TI e dos professores. Isso garante que os professores tenham todas as equipes de classe criadas e prontas para serem configuradas ao entrar. [A SDS (School Data Sync)](https://docs.microsoft.com/SchoolDataSync) é uma ferramenta gratuita do Office 365 Education que lê os dados do sistema de um registro de instituição educacional, por exemplo, um SIS (sistema de informações de alunos) ou LMS (sistema de gerenciamento de aprendizagem). O SDS usa os dados para enriquecer a configuração do Office 365 de várias maneiras, incluindo a criação de equipes de classe em massa e a manutenção da sincronização com o seu sistema de informações para que o instrutor e a associação do aluno sejam atualizados conforme as alterações no registro. O SDS pode importar dados de qualquer sistema de registro e tem conectores internos para muitos dos [fornecedores SIS](https://docs.microsoft.com/schooldatasync/what-sis-and-mis-vendors-does-school-data-sync-support) existentes do mundo. É altamente recomendável usar SDS, uma vez que fornece os seguintes benefícios.  

### <a name="benefits"></a>Benefícios

- Criações e manutenções automáticas de equipes de classe: os professores poderão entrar no Teams e começar a ensinar imediatamente.
- A sincronização de associações com o SIS/LMS para manter as alterações da associação do aluno.
- Equipe de Sucesso do Cliente EDU disponível para obter assistência de implantação gratuita.
- [Acesso antecipado ao professor](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): educadores têm tempo para preparar a equipe antes de admitir estudantes.  
- Opcionalmente cria os usuários e aplica licenças do Office 365.
- Cria grupos de segurança para usar no Office 365, incluindo a política Teams.
- Cria unidades administrativas para delegação administrativa de escopo e [Redefinição de senha do professor](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset). 
- Erro interno e tratamento de repetição, controle de retirada e estabilidade de sessão para processamento em grande escala para reduzir o trabalho dos administradores.  
- Recursos de limpeza internos para renomear e arquivar grupos e equipes quando eles estiverem obsoletos.
- [Sincronização de notas](https://docs.microsoft.com/schooldatasync/grade-sync): os professores podem fazer toda a gradação no Teams e fazer com que escreva as notas do Teams automaticamente na ficha de notas SIS. 
- [Proteção de dados do aluno](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): impedir que os alunos usem aplicativos que não são da Microsoft e acompanhem e gerenciem o consentimento dos pais. 
- Os dados importados são usados para enriquecer percepções educativas com funções de usuário, organizações (escolas) e outros dados importantes.  

### <a name="considerations"></a>Considerações

O SDS cria equipes em duas etapas. A primeira etapa cria um grupo Microsoft 365 no Azure Active Directory (Azure AD) e a segunda etapa automaticamente transforma esse grupo em uma equipe. A segunda etapa da criação de equipes é opcional no SDS. Um administrador pode não desejar criar equipes automaticamente dependendo do tempo de implantação e o número de equipes não usadas que possam resultar. Recomendamos que as instituições com 500.000 ou mais equipes desabilitem o recurso de criação automática de equipe no SDS e usem o [ método de criação da equipe ministrada pelo professor](#teacher-led-team-creation-from-office-365-class-groups).  

### <a name="get-started"></a>Introdução

Para começar, acesse [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) e contate [https://aka.ms/sdssupport](https://aka.ms/sdssupport) assistência de implantação.  

## <a name="teacher-led-team-creation-from-office-365-class-groups"></a>Criação da equipe ministrada por professores dos grupos de classe do Office 365

**Esse recurso será lançado em breve, em meados de agosto de 2020.**

A criação da equipe ministrada por professores é uma ótima opção de implantação se você quiser que os professores possam facilmente criar as classes de que precisam. Também recomendamos que as instituições com mais de 500.000 equipes usem esse método para minimizar o número de equipes criadas despropositadamente.   

Essa abordagem híbrida permite que você use o SDS para criar grupos para cada classe (recomendado) ou use a [API do Graph](https://docs.microsoft.com/graph/api/educationroot-post-classes) para criá-las por conta própria. Depois que os grupos de classe estiverem preparados, os educadores poderão converter os grupos em equipes usando o ícone **Classes sugeridas**.

:::image type="content" source="media/class-teams-edu-suggested-classes.png" alt-text="Captura de tela mostrando o ícone Classes sugeridas":::

### <a name="benefits"></a>Benefícios

- [Acesso antecipado ao professor](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): educadores têm tempo para preparar a equipe antes de admitir estudantes.  
- Reduz o número de equipes não usadas e desnecessárias. As classes são preparadas e sugeridas, mas não criadas, a menos que o professor queira usá-las. Recomendamos essa opção para grandes instituições que têm mais de 500.000 equipes para reduzir a desorganização.
- SDS
    - A sincronização de associações com o SIS/LMS para manter as alterações da associação do aluno.
    - Equipe de Sucesso do Cliente EDU disponível para obter assistência de implantação gratuita.
    - Opcionalmente cria os usuários e aplica licenças do Office 365.
    - Cria grupos de segurança para usar no Office 365, incluindo a política Teams.
    - Cria unidades administrativas para delegação administrativa de escopo e [Redefinição de senha do professor](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset).
    - Erro interno e tratamento de repetição, controle de retirada e estabilidade de sessão para processamento em grande escala para reduzir o trabalho dos administradores. 
    - Recursos de limpeza internos para renomear e arquivar grupos e equipes quando eles estiverem obsoletos. 
    - [Sincronização de notas](https://docs.microsoft.com/schooldatasync/grade-sync): os professores podem fazer toda a gradação no Teams e fazer com que escreva as notas do Teams automaticamente na ficha de notas SIS. 
    - [Proteção de dados do aluno](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): impedir que os alunos usem aplicativos que não são da Microsoft e acompanhem e gerenciem o consentimento dos pais. 
    - Os dados importados são usados para enriquecer percepções educativas com funções de usuário, organizações (escolas) e outros dados importantes.
- API do Graph
    - Maior flexibilidade e controle.
    - Não requer integração com o SDS.

### <a name="considerations"></a>Considerações

- Não totalmente automatizado e requer algumas ações dos professores.
- Os professores que não têm permissão para criar equipes ainda poderão criar equipes de grupos existentes conforme mostrado [aqui](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).
- A API do Graph exige um alto nível de experiência técnica e tempo para criar e executar o script e corrigir os problemas na criação de grupos de classe.

### <a name="get-started"></a>Introdução

Para começar a usar o método SDS, acesse [ School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) e contate a [https://aka.ms/sdssupport](https://aka.ms/sdssupport) assistência de implantação. 

Para usar o método de API do Graph, confira [API do Graph](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-1.0&tabs=http) e [Criar uma equipe de classe](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http).  

> [!NOTE]
> Para usar esse método com o SDS, você precisará ativar o recurso de criação automática da equipe em seu perfil SDS. Você também pode usar uma combinação de criação automática e de criação de equipe ministrada por professores para equipes de classe necessárias e opcionais usando dois perfis SDS.

## <a name="powershell-script-using-graph-apis"></a>Script do PowerShell usando APIs do Graph

Com o PowerShell, você pode escrever um script para criar equipes, canais e definir automaticamente as configurações. É necessário que o administrador primeiro crie o grupo, adicione professores e alunos e crie a equipe conforme descrito [aqui](https://docs.microsoft.com/graph/teams-create-group-and-team). Você também pode usar a API do Microsoft Graph para criar, configurar, duplicar e arquivar equipes. Para saber mais, confira [usar a API do Microsoft Graph para trabalhar com o Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview), [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams) e [Criar uma equipe de classe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-6-create-a-team-with-a-non-standard-base-template-type). As APIs do Graph são uma ótima maneira de ter mais controle e flexibilidade, no entanto, exige um alto nível de experiência técnica e leva mais tempo para a configuração inicial.  

### <a name="benefits"></a>Benefícios

- Maior flexibilidade e controle.
- Opção para criar equipes de acesso antecipado aos professores ou acesso imediato às equipes para o aluno.  
- Se você [Criar equipes a partir de grupos](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-4-create-a-team-from-group), os professores terão acesso antecipado e as alterações no registro do aluno no Azure AD serão sincronizadas.

### <a name="considerations"></a>Considerações

- Exige um alto nível de experiência técnica e tempo para criar e executar o script e corrigir os problemas na criação de grupos de classe.
- Sem tratamento de erros internos ou lógica de repetição.
- As alterações de associação não são sincronizadas com o SIS. 

> [!NOTE]
> As equipes de classe exigem associação a um grupo oculto, para que somente os professores e alunos dentro da classe possam ver os membros dessa classe. Para criar um grupo de classe do Office 365, confira [Criar uma equipe de classe](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http) para atender aos mesmos requisitos de privacidade.

## <a name="manual-team-creation"></a>Criação da equipe manualmente

Estudantes e professores aproveitarão ao máximo o Teams ao usá-lo com barreiras mínimas e terão a flexibilidade para adaptá-lo às suas necessidades. Uma forma dos usuários personalizarem a experiência do Teams é ter a capacidade de criar equipes que atendam às suas necessidades. Os professores configuram seu próprio tipo de classe da equipe e convidam os alunos conforme mostrado [aqui](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch). Os professores podem [adicionar alunos à equipe](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954), ao [compartilharem um código de ingresso](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f) ou ao [compartilharem um link para a equipe](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Se possível, é melhor que os professores adicionem seus alunos à equipe para garantir que eles tenham acesso e sejam notificados de que foram adicionados a uma equipe.

### <a name="benefits"></a>Benefícios

- Maior flexibilidade e controle.
- Criação e acesso imediatos à equipe.  

### <a name="considerations"></a>Considerações

- Exige ações e horas do professor.
- As participações dos alunos não são sincronizadas com o SIS e exigem gerenciamento manual.
- Não oferece aos professores acesso antecipado às suas equipes. Os alunos terão acesso imediato.

## <a name="recommended-best-practices"></a>Práticas recomendadas

- Implantação antecipada! Implante antecipadamente para garantir que tudo esteja funcionando de maneira confiável e pronta para o primeiro dia de escola. Se você estiver usando o SDS, não precisará da participação completa do aluno para iniciar a implantação SDS. Ele sincronizará os alunos quando essas informações estiverem disponíveis no SIS.
- Se você tiver mais de 500.000 equipes, recomendamos usar o [método de criação da equipe ministrada pelo professor](#teacher-led-team-creation-from-office-365-class-groups). Isso reduz as equipes não usadas e a desordem, criando apenas equipes de classe relevantes e necessárias.  
- Caso haja algum problema (por exemplo, as classes não estiverem presentes) com a criação automática de equipe e os professores precisarem delas imediatamente, eles poderão usar o [método de criação de equipe ministrada por professor](#teacher-led-team-creation-from-office-365-class-groups) para tentar novamente. [A criação manual de equipe](#manual-team-creation) é outra solução, no entanto, não mantém a participação da equipe atualizada.  
- O limite da equipe de locatários é de 500.000 equipes. Portanto, os administradores devem tentar reduzir proativamente o número de equipes não utilizadas para evitar o seu tempo de configuração. Para saber mais sobre os limites, confira [Limites e especificações para o Microsoft Teams](limits-specifications-teams.md).  
