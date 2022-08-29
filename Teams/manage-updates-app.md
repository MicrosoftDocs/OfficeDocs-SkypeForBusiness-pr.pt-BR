---
title: Gerenciar o Atualizações aplicativo para sua organização
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
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
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 66ff8f642e3e006221507953a2fff1740237aea0
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397102"
---
# <a name="manage-the-updates-app-for-your-organization-in-microsoft-teams"></a>Gerenciar o Atualizações para sua organização no Microsoft Teams

## <a name="what-is-the-updates-app"></a>O que é o Atualizações aplicativo

A Atualizações no aplicativo Microsoft Teams fornece um local centralizado para os membros da sua organização criarem, revisarem e enviarem atualizações. Ao criar modelos, você pode usar o aplicativo Atualizações para controlar tudo o que sua organização precisa. Atualizações está disponível para desktop e dispositivos móveis.

No Teams, os usuários podem obter Atualizações na loja de aplicativos do Teams. Eles verão todas as atualizações necessárias para enviar **na página Enviar** . Você pode compartilhar o [artigo Introdução Atualizações com](https://support.microsoft.com/office/get-started-in-updates-c03a079e-e660-42dc-817b-ca4cfd602e5a) seus usuários para ajudá-los a se familiarizarem usando Atualizações.

[![Imagem da página Enviar no Teams para área de trabalho.](media/updates-submit-small.png)](media/updates-submit.png#lightbox)

Os usuários podem exibir as atualizações atribuídas na **página** Revisão.

[![Imagem da página Revisão no Teams para área de trabalho.](media/updates-home-small.png)](media/updates-home.png#lightbox)

Quando um usuário recebe uma atualização, ele é exibido no feed de atividades do Teams. Os usuários também podem exibir todas as solicitações de atualização atuais e envios anteriores no Atualizações aplicativo. Além disso, qualquer pessoa pode criar modelos e enviar solicitações de atualização.

Atualizações vem com os dois modelos básicos para cenários de negócios comuns e a opção de criar seu próprio modelo. Qualquer pessoa pode criar um modelo para novos tipos de atualizações.

## <a name="example-scenario"></a>Exemplo de cenário

Os funcionários de uma loja de roupas são responsáveis por abrir e fechar a loja todos os dias. Todas as manhãs, o líder de turno preenche a atualização de abertura da Loja, que é um modelo de caixa no Atualizações aplicativo. Nesta atualização, eles descrevem quaisquer problemas com o fechamento da noite anterior, respondem perguntas sobre a limpeza da loja e relatam todos os suprimentos que precisam ser reabastecidos. Enviar uma atualização permite que eles comuniquem suas necessidades para a loja e quaisquer problemas de forma rápida e eficiente. As atualizações diárias também dão aos associados da loja uma oportunidade de realçar o que está indo bem.

Nas instalações de fabricação da loja, os funcionários realizam verificações de segurança com Atualizações dispositivos móveis.

![Imagem do modelo passo a passo de segurança semanal em um dispositivo móvel.](media/updates-mobile.png)

Enquanto isso, uma equipe de funcionários remotos está atualizando o site da loja. Eles são distribuídos entre fusos horários, portanto, reuniões de stand-up diárias não são convenientes. Em vez disso, cada um dos membros da equipe envia Atualizações relatórios diários sobre seu progresso para o líder da equipe.

[Baixe o Atualizações para](https://go.microsoft.com/fwlink/?linkid=2197649&clcid=0x409) ver mais exemplos do que você pode fazer com Atualizações.

## <a name="required-permissions-and-licenses"></a>Permissões e licenças necessárias

Você precisa de permissão para os seguintes itens implantarem Atualizações:

- Permissões para criar um banco de dados do Microsoft Dataverse.

- Uma conta no [powerautomate.microsoft.com](https://powerautomate.microsoft.com/).

- Função de administrador em seu ambiente de destino.

- Licença para Power Automate, Office 365 ou Dynamics 365.

- A licença Microsoft Forms é necessária para que os usuários configurem novos modelos.

## <a name="storage-with-microsoft-dataverse"></a>Armazenamento com o Microsoft Dataverse

O CDM (Common Data Model) é a linguagem de dados compartilhada usada por aplicativos de negócios e analíticos no Microsoft Dataverse. Ele consiste em um conjunto de esquemas de dados padronizados e extensíveis publicados pela Microsoft e nossos parceiros que permitem a consistência dos dados e seu significado em aplicativos e processos de negócios. Saiba mais sobre o [Common Data Model](/common-data-model/).

Atualizações criados com base em um modelo ainda armazenam dados no Microsoft Dataverse, como título, detalhes, ID do modelo e muito mais. Saiba mais sobre  [o Armazenamento de dados para Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Se você excluir o modelo de formulário no site Microsoft Forms, ele interromperá o modelo de Atualizações e os usuários não poderão enviar a atualização. Os usuários receberão um erro "CDB TableNotFound" ao tentar abrir um modelo que foi excluído no Microsoft Forms.

## <a name="updates-teams-app-permissions"></a>Atualizações do aplicativo Teams

O Atualizações do Teams permite que você acesse os seguintes recursos:

- Receba mensagens e dados que você fornece a ela.

- Enviar mensagens e notificações.

- Renderizar aplicativos pessoais e caixas de diálogo sem um header fornecido pelo Teams.

- Acesse suas informações de perfil, como nome, endereço de email, nome da empresa e idioma preferido.

- Receba mensagens e dados que os membros da equipe fornecem a ela em um canal.

- Enviar mensagens e notificações em um canal.

- Acesse as informações da sua equipe:
  - nome da equipe
  - lista de canais
  - lista de participantes (nomes e endereços de email dos membros da equipe)

- Use as informações da equipe para contatá-los.

## <a name="disable-the-updates-app"></a>Desabilitar o Atualizações aplicativo

O Atualizações aplicativo está disponível por padrão. Você pode desabilitar o aplicativo no Centro de administração do Teams.

  1. Entre no Centro de administração do Teams.

  2. Vá para **Aplicativos do Microsoft Teams** > **Gerenciar aplicativos**.

  3. Pesquise o Atualizações aplicativo.

     [![Captura de tela da navegação Administração central com os Aplicativos do Teams > Gerenciar Aplicativos realçados.](media/manage-updates-small.png)](media/manage-updates.png#lightbox)

  4. Selecione **Atualizações**.

  5. Selecione o alternância para desabilitar o aplicativo em sua organização.
    ![Imagem da alternância para habilitar ou desabilitar Atualizações.](media/toggle-updates.png)

## <a name="pin-updates-to-teams"></a>Fixar Atualizações no Teams

As políticas de configuração de aplicativo permitem que você personalize o Teams para fixar aplicativos que são mais importantes para seus usuários em seus usuários. Os aplicativos são fixados na barra de aplicativos , a barra ao lado do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, em que os usuários podem facilmente accessá-los.

Para fixar o aplicativo Atualizações para seus usuários, você pode editar a política global (padrão em toda a organização) ou criar e atribuir uma política de configuração de aplicativo personalizada. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Política de retenção

Atualizações criados a partir do Atualizações aplicativo são armazenados no ambiente padrão do Microsoft Dataverse, que não dá suporte a backups no momento. Saiba mais sobre como fazer [backup e restaurar ambientes - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).

Os dados armazenados no Forms não serão excluídos até que os criadores do modelo os limpem na guia formulários excluídos no Microsoft Forms Web.

## <a name="conditional-access-and-permission-policies"></a>Políticas de acesso condicional e permissão

O Atualizações no Teams atualmente não dá suporte a políticas de Acesso Condicional definidas para o Microsoft Teams.

Você pode usar políticas [de permissão de aplicativo do Teams](teams-app-permission-policies.md) para gerenciar Atualizações.

## <a name="data-limitations"></a>Limitações de dados

Cada usuário pode criar no máximo 400 modelos de Atualizações, e cada modelo pode coletar no máximo 50.000 solicitações com base na funcionalidade atual no Microsoft Forms.

## <a name="security"></a>Segurança

No aplicativo teams Atualizações, os usuários têm acesso para criar novas atualizações e exibir atualizações que eles enviaram e receberam. Os usuários não terão acesso aos Atualizações criados por outras pessoas, a menos que sejam um visualizador da solicitação.

> [!Note]
> Um usuário receberá uma função de visualizador de uma solicitação se ele fizer parte do chat ou canal em que o relatório de atualização foi criado ou se o criador do modelo o adicionar manualmente como um visualizador. Eles não terão a capacidade de tomar medidas na solicitação se não tiverem essa função quando o relatório foi criado.
