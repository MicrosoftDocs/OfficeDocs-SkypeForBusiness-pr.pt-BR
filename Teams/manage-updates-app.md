---
title: Gerenciar o aplicativo Atualizações para sua organização
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: how-to
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
description: Saiba como gerenciar o aplicativo Atualizações no Teams para usuários em sua organização.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: a17ea9ce12382439fb3f52d8e5f42264fb27d992
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131040"
---
# <a name="manage-the-updates-app-for-your-organization-in-microsoft-teams"></a>Gerenciar o aplicativo Atualizações para sua organização no Microsoft Teams

## <a name="what-is-the-updates-app"></a>Qual é o aplicativo Atualizações

O Atualizações no aplicativo Microsoft Teams fornece um local centralizado para os membros da sua organização criarem, revisarem e enviarem atualizações. Ao criar modelos, você pode usar o aplicativo Atualizações para acompanhar tudo o que sua organização precisa. Atualizações está disponível para área de trabalho e móvel.

No Teams, os usuários podem obter Atualizações na loja de aplicativos do Teams. Eles verão todas as atualizações necessárias para enviar na página **Enviar** . Você pode compartilhar o [artigo Introdução em Atualizações](https://support.microsoft.com/office/get-started-in-updates-c03a079e-e660-42dc-817b-ca4cfd602e5a) com seus usuários para ajudá-los a ficar confortáveis usando Atualizações.

[![Imagem da página Enviar no Teams para área de trabalho.](media/updates-submit-small.png)](media/updates-submit.png#lightbox)

Os usuários podem exibir atualizações atribuídas na página **Revisão** .

[![Imagem da página Revisão no Teams para área de trabalho.](media/updates-home-small.png)](media/updates-home.png#lightbox)

Quando um usuário recebe uma atualização, ele aparece no feed de atividades do Teams. Os usuários também podem exibir todas as suas solicitações de atualização atuais e envios anteriores no aplicativo Atualizações. Além disso, qualquer pessoa pode criar modelos e enviar solicitações de atualização.

Atualizações vem com modelos fora da caixa para cenários de negócios comuns e a opção de criar seu próprio modelo. Qualquer pessoa pode criar um modelo para novos tipos de atualizações.

## <a name="example-scenario"></a>Exemplo de cenário

Os funcionários de uma loja de roupas são responsáveis por abrir e fechar a loja todos os dias. Todas as manhãs, o líder de turno preenche a atualização de abertura da Loja, que é um modelo fora da caixa no aplicativo Atualizações. Nesta atualização, eles descrevem quaisquer problemas com o fechamento da noite anterior, respondem a perguntas sobre a limpeza do repositório e relatam quaisquer suprimentos que precisem ser reabastecidos. Enviar uma atualização permite que eles comuniquem suas necessidades para o repositório e quaisquer problemas de forma rápida e eficiente. As atualizações diárias também dão aos associados da loja a oportunidade de destacar o que está indo bem.

Nas instalações de fabricação da loja, os funcionários realizam verificações de segurança com Atualizações usando dispositivos móveis.

![Imagem do modelo de passo a passo de segurança semanal em um dispositivo móvel.](media/updates-mobile.png)

Enquanto isso, uma equipe de trabalhadores remotos está atualizando o site da loja. Eles estão espalhados por fusos horários, então reuniões diárias de stand-up não são convenientes. Em vez disso, cada um dos membros da equipe envia relatórios diários Atualizações sobre seu progresso para o líder da equipe.

[Baixe o lookbook Atualizações](https://go.microsoft.com/fwlink/?linkid=2197649) para ver mais exemplos do que você pode fazer com Atualizações.

## <a name="required-permissions-and-licenses"></a>Permissões e licenças necessárias

Você precisa de permissão para que os seguintes itens implantem Atualizações:

- Permissões para criar um banco de dados do Microsoft Dataverse.

- Uma conta no [powerautomate.microsoft.com](https://powerautomate.microsoft.com/).

- Função de administrador em seu ambiente de destino.

- Licença para Power Automate, Office 365 ou Dynamics 365.

- A licença para Microsoft Forms é necessária para que os usuários configurem novos modelos.

## <a name="storage-with-microsoft-dataverse"></a>Armazenamento com o Microsoft Dataverse

O CDM (Common Data Model) é a linguagem de dados compartilhada usada por aplicativos empresariais e analíticos no Microsoft Dataverse. Ele consiste em um conjunto de esquemas de dados extensíveis e padronizados publicados pela Microsoft e nossos parceiros que permitem a consistência dos dados e seu significado entre aplicativos e processos comerciais. Saiba mais sobre o [Modelo de Dados Comuns](/common-data-model/).

Atualizações que são criados a partir de um modelo ainda armazenam dados no Microsoft Dataverse, como seu título, detalhes, ID do modelo e muito mais. Saiba mais sobre  [o armazenamento de dados para Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Se você excluir o modelo de Formulário no site Microsoft Forms, ele interromperá seu modelo de Atualizações e os usuários não poderão enviar a atualização. Os usuários recebem um erro "CdB TableNotFound" ao tentar abrir um modelo que foi excluído no Microsoft Forms.

## <a name="updates-teams-app-permissions"></a>Atualizações permissões de aplicativo do Teams

O aplicativo Atualizações Teams permite que você acesse os seguintes recursos:

- Receba mensagens e dados que você fornece a ela.

- Enviar mensagens e notificações.

- Renderizar aplicativos pessoais e caixas de diálogo sem um header fornecido pelo Teams.

- Acesse suas informações de perfil, como nome, endereço de email, nome da empresa e idioma preferido.

- Receba mensagens e dados que os membros da equipe fornecem a ela em um canal.

- Enviar mensagens e notificações em um canal.

- Acesse as informações da sua equipe:
  - nome da equipe
  - lista de canais
  - listagem (nomes de membros da equipe e endereços de email)

- Use as informações da equipe para contatá-los.

## <a name="disable-the-updates-app"></a>Desabilitar o aplicativo Atualizações

O aplicativo Atualizações está disponível por padrão. Você pode desabilitar o aplicativo no Centro de administração do Teams.

  1. Entre no Centro de administração do Teams.

  2. Vá para **Aplicativos do Microsoft Teams** > **Gerenciar aplicativos**.

  3. Pesquise o aplicativo Atualizações.

     [![Captura de tela da navegação do centro de Administração com os Aplicativos do Teams > Gerenciar Aplicativos realçados.](media/manage-updates-small.png)](media/manage-updates.png#lightbox)

  4. Selecione **Atualizações**.

  5. Selecione o alternância para desabilitar o aplicativo em sua organização.
    ![Imagem do alternância para habilitar ou desabilitar Atualizações.](media/toggle-updates.png)

## <a name="pin-updates-to-teams"></a>Fixar Atualizações no Teams

As políticas de configuração do aplicativo permitem personalizar o Teams para fixar aplicativos que são mais importantes para seus usuários em seus usuários. Os aplicativos são fixados na barra de aplicativos , a barra na lateral do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, onde os usuários podem acessá-los rapidamente e facilmente.

Para fixar o aplicativo Atualizações para seus usuários, você pode editar a política global (padrão em toda a organização) ou criar e atribuir uma política personalizada na política de configuração do aplicativo. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Política de retenção

Atualizações criadas a partir do aplicativo Atualizações são armazenadas no ambiente padrão do Microsoft Dataverse, que não dá suporte a backups no momento. Saiba mais sobre como fazer [backup e restaurar ambientes - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

Os dados armazenados em Formulários não serão excluídos até que os criadores do modelo os limpem da guia **formulários excluídos** no aplicativo Web Microsoft Forms.

## <a name="conditional-access-and-permission-policies"></a>Políticas de permissão e acesso condicional

O aplicativo Atualizações no Teams atualmente não dá suporte a políticas de Acesso Condicional definidas para o Microsoft Teams.

Você pode usar [políticas de permissão de aplicativo do Teams](teams-app-permission-policies.md) para gerenciar Atualizações.

## <a name="data-limitations"></a>Limitações de dados

Cada usuário pode criar no máximo 400 modelos de Atualizações e cada modelo pode coletar no máximo 50.000 solicitações com base no recurso atual em Microsoft Forms.

## <a name="security"></a>Segurança

No aplicativo teams Atualizações, os usuários têm acesso para criar novas atualizações e exibir atualizações que enviaram e receberam. Os usuários não terão acesso a Atualizações criadas por outras pessoas, a menos que sejam um visualizador da solicitação.

>[!Note]
> Um usuário recebe uma função de visualizador de uma solicitação se ele faz parte do chat ou canal em que o relatório de atualização foi criado ou o criador do modelo os adiciona manualmente como visualizador. Eles não terão a capacidade de agir na solicitação se não receberem essa função quando o relatório foi criado.
