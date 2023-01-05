---
title: Gerenciar acesso do usuário ao Education Insights
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Gerenciar acesso do usuário ao Education Insights no Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7203c9bda1a6e5c2bf9d90b490492fe7bbc3f64c
ms.sourcegitcommit: 78fbfcf4a1aafce5d39eea79c9461a9fc1bb3d38
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2023
ms.locfileid: "69707803"
---
# <a name="manage-user-access-to-education-insights"></a>Gerenciar acesso do usuário ao Education Insights

Este documento descreve as etapas necessárias para gerenciar o acesso do usuário ao [Education Insights no Microsoft Teams](class-insights.md).

You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists. Educators are *automatically* given permission when they own a class team.

Para fornecer o Insights no nível da organização, você deve [importar dados do Sistema de Informações do Aluno (SIS)](education-insights-sis-data-sync.md) de forma que o Insights tenha estrutura hierárquica do sistema educacional mapeada corretamente.

> [!NOTE]
> Apenas o Administrador Global pode gerenciar o acesso do usuário ao Insights.

> [!TIP]
> Recomendamos que você habilite o insights para todos seus líderes de educação para que eles tenham os dados para entender cada escola, e a capacidade de identificar rapidamente os problemas e fornecer suporte aos seus educadores. Mesmo que você esteja executando um projeto piloto, ainda pode ser útil manter o Insights habilitado para todos os líderes da educação, mas só direcionar as comunicações para o grupo piloto de usuários.

## <a name="manage-permissions"></a>Gerenciar permissões

* Abra o aplicativo Insights, clique em **Configurações** e, selecione **Permissões de usuário**

:::image type="content" source="media/insights-user-permissions.png" alt-text="Configurações.":::

> [!NOTE]
> Quando você fornece permissão para um nível organizacional, o usuário pode ver todas as unidades da organização abaixo dele.
> 
> Somente dê permissão aos líderes escolares que precisam delas e somente às unidades organizacionais pelas quais são responsáveis. Se você não tiver certeza se é necessária a permissão do usuário para uma organização específica, consulte os especialistas em assuntos de privacidade de sua instituição, tais como o pessoal do departamento jurídico ou do RH.

> [!IMPORTANT]
> Depois de atribuir permissões pela primeira vez, os usuários poderão exibir os dados no aplicativo somente se pelo menos **dois** usuários tiverem acessado o aplicativo. Esse requisito ajuda a garantir que o fuso horário dos dados esteja configurado corretamente e que os dados sejam exibidos com precisão para todos os usuários. Se os usuários estiverem enfrentando problemas ao acessar os dados após a concessão de permissões, verifique se pelo menos dois usuários acessaram o aplicativo.

## <a name="role-based-permissions"></a>Permissões baseadas em função

If you use [SDS V2.1 file format](/schooldatasync/sds-v2.1-csv-file-format) or [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format), you can import all roles and the full hierarchy of schools within the education system. This complete mapping enables you to assign permissions to roles. 

> [!NOTE]
> Quando um usuário recebe uma função, ele recebe automaticamente as permissões corretas para ver os dados relevantes para ele.
>
> Se um usuário não estiver mais em uma função, sua permissão para essa função será revogada automaticamente (embora ele ainda possa ter permissões individuais).

* Se necessário, clique com o botão direito na guia **permissões baseadas em função**.

  Você verá uma lista das funções em sua organização educacional, o nível nessa hierarquia para cada um deles, quantos usuários são atribuídos a essa função e o nível de permissão da função. 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="Permissões baseadas em funções":::
  
  Se houver uma função em mais de um nível de organização, essa função aparecerá várias vezes, uma vez para cada nível. Na captura de tela, temos diretores em nível de escola, distrito e departamento, portanto, há três linhas para 'diretor'.
  
* Para cada função, clique no ícone de lápis para selecionar o nível de permissão. O padrão é que a função não tem permissão para ver Insights.
* Selecione o nível de permissão:**Exibir dados de sua organização** ou **Nenhum**.

  :::image type="content" source="media/insights-role-based-permissions-panel.png" alt-text="Painel de permissões baseadas em funções.":::
  
  Se você vir um usuário na lista que precisa de um nível de permissão com mais nuances, ajuste sua função e/ou organização nos [dados importados do seu SIS](education-insights-sis-data-sync.md) e [conceda a eles permissões individuais](#grant-individual-permission-to-a-user) (se necessário )

* Clique em **Salvar alterações**.

  Esse nível de permissão agora é atribuído automaticamente a qualquer novo usuário com essa função e nível de organização. O usuário verá os dados de todas as unidades da organização em seu nível de hierarquia e abaixo dele.  


## <a name="individual-permissions"></a>Permissões individuais

Use permissões individuais para ajustar a permissão de um usuário ou atribuir permissões para cada usuário se você não tiver usado o SDS V2 para importar dados do SIS para a organização.

* Clique na guia **Permissões individuais**.
  
  Você verá que os usuários em sua organização educacional concederam permissão individual. 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="Permissões individuais.":::
  
### <a name="grant-individual-permission-to-a-user"></a>Conceder permissão individual a um usuário
* Clique em **Conceder permissão individual** na parte superior esquerda da tela.
* Insira o nome de usuário ou endereço de email de cada usuário.
* Selecionar o nível de permissão:
  * **Todos** significa que o usuário vê todas as unidades da organização em todos os níveis. Isso é usado muito raramente.
  * **Organização específica** significa que o usuário vê a unidade organizacional selecionada e todas as unidades da organização abaixo dela. Comece a digitar e selecione a unidade organizacional na lista.
* Clique em **Conceder permissão** para salvar.

### <a name="change-the-individual-permission-of-a-user"></a>Alterar a permissão individual de um usuário
* Para o usuário relevante, clique no ícone de lápis para selecionar o nível de permissão individual.
* Selecionar o nível de permissão:
  * **Todos** significa que o usuário vê todas as unidades da organização em todos os níveis. Isso é usado muito raramente.
  * **Organização específica** significa que o usuário vê a unidade organizacional selecionada e todas as unidades da organização abaixo dela. Comece a digitar e selecione a unidade organizacional na lista.
  * **Nenhum** significa que o usuário só vê as unidades da organização atribuídas automaticamente por sua função (se houver).
  
  :::image type="content" source="media/insights-individual-permissions-panel.png" alt-text="Painel de permissões individuais.":::

* Clique em **Salvar alterações** para salvar.
