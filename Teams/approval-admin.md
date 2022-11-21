---
title: Gerenciar o aplicativo Aprovações no Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: farhazk
manager: samanro
ms.topic: how-to
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Saiba como gerenciar o aplicativo Aprovações para sua organização no Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: cbedcfb7215adbde9ee8b8dd2afb3e88422e28c2
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131180"
---
# <a name="manage-the-approvals-app-in-microsoft-teams"></a>Gerenciar o aplicativo Aprovações no Microsoft Teams

O aplicativo Aprovações está disponível como um aplicativo pessoal para todos os usuários do Microsoft Teams.
O aplicativo Aprovações oferece uma maneira simples de levar auditoria, conformidade, responsabilidade e fluxos de trabalho para Aprovações estruturadas e não estruturadas em Equipes.

 ![mostra o aplicativo de aprovações.](media/approvals-selection.png)

Os usuários podem fixar o aplicativo Aprovações para salvá-lo na barra de menus.

 ![mostra o aplicativo de aprovações com a opção pin.](media/approvalApp-pin.png)

A primeira aprovação criada a partir do aplicativo Approvals disparará o provisionamento da Solução de Aprovação no ambiente padrão do Microsoft Dataverse. As aprovações criadas a partir do aplicativo Approvals serão armazenadas no ambiente padrão do Microsoft Dataverse.

Este artigo descreve os requisitos e as funções do aplicativo Aprovações.

> [!NOTE]
> Esse recurso ainda não foi lançado para usuários do GCCH (Government Community Cloud High) e do Departamento de Defesa (DOD).

## <a name="required-permissions-and-licenses"></a>Permissões e licenças necessárias

Para implantar o aplicativo Aprovações, você precisa de permissão para os seguintes itens:

- Permissões para criar um banco de dados do Microsoft Dataverse.

- Uma conta no [powerautomate.microsoft.com](https://powerautomate.microsoft.com/)

- Função de administrador no ambiente de destino.

- Licença para [Power Automate](/power-automate/get-started-approvals), Office 365 ou Dynamics 365.

- A licença para Microsoft Forms é necessária para que os usuários configurem novos modelos de aprovação.

Para usar o aplicativo Aprovações, você precisa de uma licença para o Power Automate e sua conta é adicionada automaticamente à função Aprovações Usuário no ambiente de destino em sua primeira atribuição de aprovação.

## <a name="storage-with-microsoft-dataverse"></a>Armazenamento com o Microsoft Dataverse

O CDM (Common Data Model) é a linguagem de dados compartilhada usada por aplicativos empresariais e analíticos no Microsoft Dataverse. Ele consiste em um conjunto de esquemas de dados extensíveis e padronizados publicados pela Microsoft e nossos parceiros que permitem a consistência dos dados e seu significado entre aplicativos e processos comerciais. Saiba mais sobre o [dados comuns do Microsoft Power Platform](/power-automate/get-started-approvals).

Saiba mais sobre o fluxo [de trabalho aprovação](/power-automate/modern-approvals).

As aprovações criadas a partir de um modelo ainda armazenam dados no Microsoft Dataverse, como seu título, detalhes, ID do modelo e muito mais. As respostas enviadas na solicitação de aprovação são armazenadas em Formulários. Saiba mais sobre [o armazenamento de dados para Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Se você excluir o modelo de Formulário no site Microsoft Forms, ele interromperá seu modelo de aprovação e os usuários não poderão iniciar a solicitação. Os usuários recebem um erro "CdB TableNotFound" ao tentar abrir um modelo de Aprovação que é excluído no Microsoft Forms.

Modelos com escopo de organização compartilham o mesmo tempo de vida do locatário e os modelos com escopo de equipe compartilham o mesmo tempo de vida da equipe. Portanto, excluir permanentemente a equipe exclui os modelos relacionados.

## <a name="approvals-teams-app-permissions"></a>Permissões do aplicativo Aprovações do Teams

O aplicativo Aprovações Teams permite que você acesse os seguintes recursos:

- Receba mensagens e dados que você fornece a ela.

- Enviar mensagens e notificações.

- Renderizar aplicativos pessoais e caixas de diálogo sem um header fornecido pelo Teams.

- Acesse suas informações de perfil, como nome, endereço de email, nome da empresa e idioma preferido.

- Receba mensagens e dados que os membros da equipe fornecem a ela em um canal.

- Enviar mensagens e notificações em um canal.

- Acesse as informações da sua equipe:
  - nome da equipe
  - lista de canais
  - lista de lista (nomes e endereços de email dos membros da equipe).

- Use as informações da equipe para contatá-los.

Permissões de modelo de aprovação

- Todos os proprietários de equipe podem criar um modelo de aprovação para equipes que possuem.

- Quando um administrador cria um modelo para toda a organização pela primeira vez, ele criará automaticamente um novo grupo do Azure Active Directory (AAD) para todos os administradores do locatário, incluindo os administradores de serviço global e do Teams. Esses administradores são adicionados como proprietários do grupo, para que possam cogerenciar modelos organizacionais. Os administradores que são novos na organização após a criação da equipe precisam ser adicionados manualmente como proprietários de grupo para que tenham as mesmas permissões para gerenciar modelos em toda a organização.

> [!Note]
> Se um administrador excluir o grupo, você terá um mês para restaurá-lo no portal do Azure Active Directory (AAD) para restaurar todos os dados relacionados. Após um mês ou se o administrador excluir esse grupo na lixeira, você perderá todos os dados relacionados.

## <a name="disable-the-approvals-app"></a>Desabilitar o aplicativo Aprovações

O aplicativo Aprovações está disponível por padrão. Você pode desabilitar o aplicativo no Centro de administração do Teams.

  1. Entre no Centro de administração do Teams.

  2. Vá para **Aplicativos do Microsoft Teams** > **Gerenciar aplicativos**.

  3. Procure o aplicativo Aprovações.

     ![mostra a navegação do centro de Administração com os Aplicativos do Teams > Gerenciar Aplicativos realçados.](media/manage-approval-apps.png)

  4. Selecione **Aprovações**.

  5. Selecione o alternância para desabilitar o aplicativo em sua organização.

     :::image type="content" alt-text="mostra os detalhes do aplicativo Aprovações." source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="pin-approvals-to-teams"></a>Fixar aprovações no Teams

### <a name="use-the-tailored-frontline-app-experience-to-pin-approvals-and-other-apps-to-teams"></a>Usar a experiência de aplicativo de linha de frente personalizada para fixar Aprovações e outros aplicativos no Teams

A experiência de aplicativo de linha de frente personalizada no Teams fixa os aplicativos mais relevantes no Teams para usuários que têm uma [licença F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Os aplicativos fixados incluem Aprovações, Walkie Talkie, Tarefas e Turnos. Por padrão, esse recurso está ativado, dando aos seus trabalhadores de linha de frente uma experiência fora da caixa que é adaptada às suas necessidades.

Os aplicativos são fixados na barra de aplicativos , a barra na lateral do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, onde os usuários podem acessá-los rapidamente e facilmente.

Para saber mais, incluindo como a experiência funciona com políticas de aplicativo definidas, confira [Adaptar aplicativos do Teams para seus trabalhadores de linha de frente](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

### <a name="use-an-app-setup-policy-to-pin-approvals-to-teams"></a>Usar uma política de configuração de aplicativo para fixar aprovações no Teams

As políticas de configuração do aplicativo permitem personalizar o Teams para fixar aplicativos que são mais importantes para seus usuários em seus usuários.

Para fixar o aplicativo Aprovações para seus usuários, você pode editar a política global (padrão em toda a organização) ou criar e atribuir uma política personalizada na política de configuração do aplicativo. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Política de retenção

As aprovações criadas a partir do aplicativo Approvals são armazenadas no ambiente padrão do Microsoft Dataverse, que não dá suporte a backups no momento. Saiba mais sobre como fazer [backup e restaurar ambientes - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

Os dados armazenados em Formulários não serão excluídos até que os proprietários da equipe os limpem da guia **formulários excluídos** no aplicativo Web Microsoft Forms.

## <a name="conditional-access-policies"></a>Políticas de acesso condicional

Atualmente, o aplicativo Approvals no Teams não dá suporte a políticas de acesso condicional definidas para o Microsoft Teams.

## <a name="data-limitations"></a>Limitações de dados

Cada equipe pode conter no máximo 400 modelos de aprovações e cada modelo pode coletar no máximo 50.000 solicitações com base no recurso atual em Microsoft Forms.

## <a name="auditing"></a>Auditoria

O aplicativo Approvals registra eventos de auditoria no Centro de Conformidade e Segurança do Microsoft 365. Você pode exibir o log de auditoria.

1. Vá para o Site de Conformidade do Microsoft 365.

2. Selecione a **seção** Auditoria.

3. Procure atividades em atividades em **de aprovação do Microsoft Teams**.

Você pode procurar as seguintes atividades:

- Criar nova solicitação de aprovação

- Exibir detalhes da solicitação de aprovação

- Solicitação de aprovação aprovada

- Solicitação de aprovação rejeitada

- Solicitação de aprovação cancelada

- Solicitação de aprovação compartilhada

- Arquivo anexado à solicitação de aprovação

- Solicitação de aprovação reatribuida

- Assinatura eletrônica adicionada à solicitação de aprovação

- Visualizar detalhes da solicitação de assinatura eletrônica

- Solicitação de assinatura eletrônica revisada

- Solicitação de assinatura eletrônica cancelada

- Criar um novo modelo

- Editar um modelo existente

- Habilitar/desabilitar um modelo

- Modelo visualizado

Para obter acesso a mais aprovações de auditoria no Power Automate, habilite e configure a auditoria no ambiente padrão para as entidades de aprovação primária Aprovação, Solicitação de Aprovação e Resposta de Aprovação. Operações de criação, atualização e exclusão são eventos auditáveis para registros de Aprovação. Saiba mais sobre [dados de Auditoria e atividade do usuário para segurança e conformidade - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).

A auditoria pode ser personalizada ainda mais no [de Conformidade e Segurança do Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Para usar os relatórios pré-configurados, entre em Segurança e Conformidade do Microsoft 365.

2. Selecione **pesquisa e investigação**.

3. Pesquise no log de Auditoria e selecione **atividades do Dynamics 365** dados.

Saiba mais sobre [registro em log de atividades de aplicativos orientados por modelos e dados de aplicativos do Microsoft Dataverse - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Segurança

No aplicativo Aprovações de Equipes, os usuários têm acesso para criar novas Aprovações e exibir Aprovações que enviaram e receberam. Os usuários não terão acesso às Aprovações criadas por outras pessoas, a menos que sejam respondentes ou visualizadores da solicitação.

>[!Note]
> Um usuário recebe uma função de visualizador de uma solicitação se fizer parte do chat ou canal em que a aprovação foi criada. Ela não terá a capacidade de tomar medidas na solicitação caso não tenha sido concedida essa função quando a aprovação foi criada.

## <a name="approvals-e-signature-integration"></a>Aprova a integração de assinatura eletrônica

Para usar o recurso de assinatura eletrônica do aplicativo Approvals, você precisa de uma licença para o provedor de assinatura eletrônica específico que deseja usar. Para obter uma licença para sua organização, você precisará acessar o site do provedor.

### <a name="enable-or-disable-e-signature-providers"></a>Habilitar ou desabilitar provedores de assinatura eletrônica

Você pode usar o centro de administração do Teams para controlar, quais provedores de assinatura eletrônica de terceiros estão disponíveis para seus usuários no aplicativo Aprovações. Por padrão, os provedores de assinatura eletrônica estão habilitados no aplicativo Aprovações. Quando você desabilitar um provedor de assinatura eletrônica, seus usuários não terão acesso a esse provedor quando criarem aprovações. Seus usuários também não poderão exibir solicitações de assinatura eletrônica que foram criadas usando esse provedor.

1. No painel esquerdo do centro de administração do Teams, acesse Aplicativos  > **do Teams****Gerenciar aplicativos**.
2. Pesquise o aplicativo Aprovações e selecione-o.
3. Acesse a guia **Configurações** e, em seguida, faça um ou mais dos seguintes procedimentos:

    - Para habilitar ou desabilitar o Adobe Sign, alterne o alternância para **Ativado** ou **Desativado**.
    - Para habilitar ou desabilitar o DocuSign, alterne o alternância para **Ativado** ou **Desativado**.
4. Selecione **Enviar**.

As aprovações de assinatura eletrônica criadas a partir do aplicativo Approvals são armazenadas no ambiente de nuvem do provedor selecionado. Para exportar dados sobre assinaturas eletrônicas, você precisará ir para o site do provedor. Para obter mais informações sobre armazenamento, exportação e retenção de contratos de assinatura eletrônica, consulte a documentação do provedor.
