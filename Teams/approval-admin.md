---
title: Disponibilidade do aplicativo Aprovações no Teams
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Saiba mais sobre a disponibilidade do aplicativo Aprovações no Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f3b1942e1d9b6e93d78694c2b02027bf32c5d7d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726210"
---
# <a name="teams-approvals-app-availability"></a>Disponibilidade dos aplicativos de aprovação do Teams

O aplicativo Aprovações está disponível como um aplicativo pessoal para todos os usuários do Microsoft Teams.
O aplicativo Aprovações oferece uma maneira simples de levar auditoria, conformidade, responsabilidade e fluxos de trabalho para Aprovações estruturadas e não estruturadas em Equipes.

 ![mostra o aplicativo aprovações.](media/approvals-selection.png)

Os usuários podem fixar o aplicativo Aprovações para salvá-lo na barra de menus.

 ![mostra o aplicativo de aprovações com a opção pin.](media/approvalApp-pin.png)

A primeira aprovação criada a partir do aplicativo Aprovações acionará o provisionamento da Solução de Aprovação no ambiente padrão de CDS (Serviço de Dados Comuns). As aprovações criadas a partir do aplicativo Aprovações serão armazenadas no ambiente de CDS padrão.

Este artigo descreve os requisitos e as funções do aplicativo Aprovações.

> [!NOTE]
> Esse recurso ainda não foi lançado para usuários Nuvem da Comunidade Governamental (GCC), Nuvem da Comunidade Governamental High (GCCH) e Departamento de Defesa (DOD).

## <a name="required-permissions-and-licenses"></a>Permissões e licenças necessárias

Para implantar o aplicativo Aprovações, você precisa de permissão para os seguintes itens:

- Permissões para criar um banco de dados de CDS da Microsoft.

- Uma conta em [flow.microsoft.com](https://flow.microsoft.com/)

- Função de administrador no ambiente de destino.

- Licença para um [Power Automate](/power-automate/get-started-approvals), um Office 365 ou um Dynamics 365.

- A licença do Microsoft Forms é necessária para os usuários configurarem novos modelos de aprovação.

Para usar o aplicativo Aprovações, você precisa de uma licença para Power Automate e sua conta será adicionada automaticamente à função Aprovações Usuário no ambiente de destino em sua primeira atribuição de aprovação.

## <a name="storage-with-cds"></a>Armazenamento com CDS

O CDM (Modelo de Dados Comum) é a linguagem de dados compartilhada usada por aplicativos de negócios e analíticos no CDS. Ele consiste em um conjunto de esquemas de dados extensíveis padronizados publicados pela Microsoft e por nossos parceiros que permitem a consistência dos dados e seu significado em aplicativos e processos empresariais. Saiba mais sobre o [dados comuns do Microsoft Power Platform](/power-automate/get-started-approvals).

Saiba mais sobre o fluxo [de trabalho aprovação](/power-automate/modern-approvals).

As aprovações criadas a partir de um modelo ainda armazenam dados em CDS, como título, detalhes, ID do modelo e muito mais. As respostas enviadas na solicitação de aprovação são armazenadas em Formulários. Saiba mais sobre  [o armazenamento de dados do Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Se você excluir o modelo de formulário no site do Microsoft Forms, ele quebrará seu modelo de Aprovação e os usuários não poderão iniciar a solicitação. Os usuários receberão um erro "CDB TableNotFound" ao tentar abrir um modelo de Aprovação que foi excluído no Microsoft Forms.

Os modelos de aprovação são armazenados no Substrate Data Armazenamento (SDS), que é uma plataforma de armazenamento compatível usada internamente apenas dentro da Microsoft. Os modelos de escopo da organização são armazenados em "fragmento de locatário" do SDS, e os modelos com escopo de equipe são armazenados em "fragmentos de grupo" do SDS. Isso significa que os modelos com escopo organizacional compartilham o mesmo tempo de vida dos modelos de locatário e de equipe compartilham o mesmo tempo de vida da equipe. Portanto, excluir permanentemente a equipe exclui os modelos relacionados.

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

Permissões do modelo de aprovação

- Todos os proprietários de equipe podem criar um modelo de aprovação para equipes que eles próprios têm.

- Quando um Administrador cria um modelo para toda a organização pela primeira vez, ele criará automaticamente uma nova equipe de Teams para todos os administradores do locatário, incluindo os administradores de serviço globais e de equipe. Esses administradores serão adicionados como proprietários da equipe, para que possam co-gerenciar modelos organizacionais. Os administradores novos na organização após a criação da equipe precisam ser adicionados manualmente como proprietários de equipe para que tenham as mesmas permissões para gerenciar modelos de toda a organização.

> [!Note]
> Se um administrador excluir a equipe, você terá um mês para restaurá-la no portal Azure Active Directory (AAD) para restaurar todos os dados relacionados. Após um mês ou se o administrador excluir essa equipe dentro da lixeira, você perderá todos os dados relacionados.

## <a name="disable-the-approvals-app"></a>Desabilitar o aplicativo Aprovações

O aplicativo Aprovações está disponível por padrão. Você pode desabilitar o aplicativo no Centro de administração do Teams.

  1. Entre no Centro de administração do Teams.

  2. Expanda **aplicativos Teams** e selecione **Gerenciar aplicativos**.

  3. Procure o aplicativo Aprovações.

     ![mostra a navegação do Centro de administração com Teams Aplicativos > Gerenciar Aplicativos realçadas.](media/manage-approval-apps.png)

  4. Selecione Aprovações.

  5. Selecione o alternância para desabilitar o aplicativo em sua organização.

     ![mostra os detalhes do aplicativo Aprovações.](media/approvals-details.png)

## <a name="retention-policy"></a>Política de retenção

As aprovações criadas a partir do Aplicativo Aprovações são armazenadas no ambiente de CDS padrão, que não dá suporte a backups no momento. Saiba mais sobre como fazer [backup e restaurar ambientes - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

Os dados armazenados no Forms não serão excluídos até que os proprietários da equipe os limpem da guia **formulários** excluídos no aplicativo Web do Microsoft Forms.

## <a name="data-limitations"></a>Limitações de dados

Cada equipe pode conter no máximo 400 modelos de aprovações, e cada modelo pode coletar no máximo 50.000 solicitações com base na funcionalidade atual no Microsoft Forms.

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

- Detalhes da solicitação de assinatura eletrônica exibida

- Solicitação de assinatura eletrônica revisada

- Solicitação de assinatura eletrônica cancelada

- Criar um novo modelo

- Editar um modelo existente

- Habilitar/desabilitar um modelo

- Modelo exibido

Para obter acesso a mais aprovações de auditoria no Flow, habilita e configure a auditoria no ambiente padrão para as entidades de aprovação principais Aprovação, Solicitação de Aprovação e Resposta de Aprovação. Operações de criação, atualização e exclusão são eventos auditáveis para registros de Aprovação. Saiba mais sobre [dados de Auditoria e atividade do usuário para segurança e conformidade - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).

A auditoria pode ser personalizada ainda mais no [de Conformidade e Segurança do Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Para usar os relatórios pré-configurados, entre em Segurança e Conformidade do Microsoft 365.

2. Selecione **pesquisa e investigação**.

3. Pesquise no log de Auditoria e selecione **atividades do Dynamics 365** dados.

Saiba mais sobre [registro em log de atividades de aplicativos orientados por modelos e dados de aplicativos do Microsoft Dataverse - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Segurança

No aplicativo Aprovações de Equipes, os usuários têm acesso para criar novas Aprovações e exibir Aprovações que enviaram e receberam. Os usuários não terão acesso às Aprovações criadas por outras pessoas, a menos que sejam respondentes ou visualizadores da solicitação.

> [!Note]
> Um usuário terá uma função de visualizador de uma solicitação se ele for parte do chat ou canal no qual a aprovação foi criada. Ela não terá a capacidade de tomar medidas na solicitação caso não tenha sido concedida essa função quando a aprovação foi criada.

## <a name="approvals-e-signature-integration"></a>Aprova a integração de assinatura eletrônica

As aprovações de assinatura eletrônica criadas a partir do aplicativo Aprovações são armazenadas no ambiente de nuvem do provedor selecionado. Para obter mais informações sobre o armazenamento em torno do contrato de assinatura eletrônica, consulte a documentação de armazenamento do provedor selecionado.

Para usar o recurso de assinatura eletrônica do aplicativo Aprovações, você precisa dos seguintes itens:

- Licença para o provedor de assinatura eletrônica específico que você está escolhendo usar. Para obter uma licença para sua organização, você precisará acessar o site do provedor.

Para a funcionalidade de assinatura eletrônica Aprovações, parceiros de assinatura de terceiros aparecerão no aplicativo Teams Aprovações por padrão. Você pode desabilitar provedores de assinatura eletrônica específicos acessando as configurações do aplicativo no Teams de administração.

1. No centro Teams de administração, em Gerenciar **aplicativos,** selecione o aplicativo Aprovações e escolha **Configurações**. 

2. Cada provedor de assinatura eletrônica tem uma alternância ao lado dele que está na posição on (à direita) por padrão. Deslize a alternância para a esquerda para desabilitar um provedor de assinatura eletrônica específico. Se um administrador Teams desabilitar um provedor, os usuários finais não verão o provedor ao criar uma aprovação. Os usuários finais também não poderão exibir quaisquer solicitações de assinatura eletrônica que foram feitas com esse provedor.

Aprovações de assinatura eletrônica criadas a partir do Aplicativo de Aprovações são armazenadas na nuvem do provedor selecionado. Portanto, você precisará acessar o site do provedor para exportar quaisquer dados sobre assinaturas eletrônicas. Consulte a documentação do provedor sobre exportação e retenção desses contratos.
