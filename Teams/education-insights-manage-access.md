---
title: Gerenciar acesso do usuário ao Education Insights
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Gerenciar acesso do usuário ao Education Insights no Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145928"
---
# <a name="manage-user-access-to-education-insights"></a>Gerenciar acesso do usuário ao Education Insights

Este documento descreve as etapas necessárias para gerenciar o acesso do usuário ao [Education Insights no Microsoft Teams](class-insights.md).

Você precisa fornecer permissões para gestores escolares, inspetores, diretores de escola, professores-gestores, conselheiros, coordenadores pedagógicos, diretores de programas, assistentes sociais e psicólogos. Os educadores *automaticamente* recebem permissão quando possuem uma equipe de classe.

Para fornecer o Insights no nível da organização, você deve [importar dados do Sistema de Informações do Aluno (SIS)](education-insights-sis-data-sync.md) de forma que o Insights tenha estrutura hierárquica do sistema educacional mapeada corretamente.

> [!NOTE]
> Apenas o Administrador Global pode gerenciar o acesso do usuário ao Insights.

> [!TIP]
> Recomendamos que você habilite o insights para todos seus líderes de educação para que eles tenham os dados para entender cada escola, e a capacidade de identificar rapidamente os problemas e fornecer suporte aos seus educadores. Mesmo que você esteja executando um projeto piloto, ainda pode ser útil manter o Insights habilitado para todos os líderes da educação, mas só direcionar as comunicações para o grupo piloto de usuários.



## <a name="grant-permissions"></a>Conceda permissões.

* Abra o aplicativo Insights, clique em **Configurações** e, selecione **Permissões de usuário**

:::image type="content" source="media/insights-user-permissions.png" alt-text="Configurações":::

* Selecione **Adicionar usuários**.
* Insira o nome de usuário ou endereço de email de cada usuário.
* Selecionar o nível de permissão:
  * **Acesso a toda organização** significa que o usuário vê todas as unidades da organização em todos os níveis.
  * **Acesso a escolas específicas** significa que o usuário vê as escolas selecionadas. Comece a digitar e selecione a escola a partir da lista. Você pode adicionar várias escolas simultaneamente.
* Clique **Adicionar novos usuários**.

:::image type="content" source="media/insights-add-users.png" alt-text="Conceder permissões":::

> [!NOTE]
> Somente dê permissão aos líderes escolares que precisam delas e somente às unidades organizacionais pelas quais são responsáveis. Se você não tiver certeza se é necessária a permissão do usuário para uma organização específica, consulte os especialistas em assuntos de privacidade de sua instituição, tais como o pessoal do departamento jurídico ou do RH.

## <a name="edit-permissions"></a>Editar permissões
* Selecione um usuário específico e, em seguida, selecione **Editar permissões**.
* Atualize o nível de permissão ou a lista de escolas, e clique em **Atualizar permissões**.

:::image type="content" source="media/insights-edit-users.png" alt-text="Editar permissões":::

## <a name="remove-permissions"></a>Remover permissões
* Selecione o usuário que você deseja remover e, em seguida, selecione **Remover usuários**.
* Esses usuários não têm mais acesso ao Insights a nível da organização, mas ainda poderão acessar o Insights a nível de classe se possuírem uma equipe de classe.

:::image type="content" source="media/insights-remove-users.png" alt-text="Remover permissões":::
