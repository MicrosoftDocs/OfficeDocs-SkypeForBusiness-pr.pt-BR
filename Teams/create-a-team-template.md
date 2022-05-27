---
title: Criar um modelo de equipe personalizado no Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: aaglick
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como criar um modelo de equipe personalizado no Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b313df288488de22e99943120ffd0fd94d34210
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675563"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Criar um modelo de equipe personalizado no Microsoft Teams

**Ainda não há suporte para modelos personalizados para clientes EDU.**

Um modelo de equipe personalizado é uma estrutura de equipe predefinida com um conjunto de canais, guias e aplicativos. Você pode desenvolver um modelo que ajuda a criar o espaço de colaboração certo rapidamente. Seu modelo de equipe personalizado usa suas configurações preferenciais.  

<br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4P5rx]


Para começar:

1. Entre no Centro de administração do Teams.

2. No painel de navegação esquerdo, **expanda Teams** >  **modelos de conjunto**.

3. Selecione **Adicionar**.

    ![Uma imagem da caixa de diálogo Modelos de equipe com Adicionar realçado.](media/team-templates-new.png)

4. Na seção **Modelos de equipe** , selecione **Criar um novo modelo**.

5. Na seção **Configurações de modelo** , preencha os seguintes campos e selecione **Avançar**:
    - Nome do modelo
    - Descrições curtas e longas do modelo
    - Visibilidade da localidade  

    ![Uma imagem da caixa de diálogo de nomenclatura de configurações de modelos de equipe.](media/template-add-a-name.png)

6. Na seção **canais, guias e aplicativos** , adicione todos os canais e aplicativos de que sua equipe precisa.

    1. Na seção **Canais** , selecione **Adicionar**.
    2. Na caixa **de diálogo** Adicionar, nomeie o canal.
    3. Adicione uma descrição.
    4. Decida se o canal deve ser mostrado por padrão.
    5. Pesquise um nome de aplicativo que você deseja adicionar ao canal.
    6. Selecione **Aplicar** quando terminar.

    ![Uma imagem da tela canais, guias e aplicativos de modelos de equipe.](media/template-channels-tabs-apps.png)

8. Selecione **Enviar** quando concluído.

Seu novo modelo é exibido na lista **de modelos de** equipe. O modelo pode ser usado para criar uma equipe no Teams.

> [!Note]
> Pode levar até 24 horas para que os usuários das equipes vejam uma alteração de modelo personalizada na galeria.

## <a name="customizing-website-tab-apps"></a>Personalizando aplicativos da Guia do Site

> [!Note]
> Esse recurso está em versão prévia antecipada

Talvez você queira especificar URLs para guias de site para canais em modelos de equipe personalizados. Os usuários finais que criam equipes com modelos terão guias de site predefinidas para a URL do site especificada.

Para começar:

1. Crie um novo modelo de equipe ou edite um modelo de equipe existente.

2. Na seção Canais, adicione um novo canal ou selecione um canal existente e selecione **Editar**.

3. Na seção **Adicionar um aplicativo para este modelo** , adicione um aplicativo site.

    ![adicionar um aplicativo para esta opção de modelo.](media/add-an-app-template.png)

4. Selecione o ícone de edição e insira a URL de sua escolha.

    ![adicionar uma URL de aplicativo.](media/add-url-app-template.png)

5. Selecione **Salvar** para as edições do aplicativo de guia e, em seguida, **selecione Aplicar** para salvar suas alterações.

## <a name="known-issues"></a>Problemas conhecidos

**Problema**: se você criou uma equipe com base em um modelo personalizado que continha guias personalizadas adicionais, poderá ver guias em branco no lugar de seus aplicativos de guia personalizados. Suas guias padrão (como **Postagens****, Arquivos** e **Wiki**) serão exibidas conforme o esperado.

**Solução**: para corrigir esse problema, remova a guia personalizada e adicione uma nova guia com o mesmo aplicativo. Se você não tiver permissões para remover a guia personalizada e adicionar uma nova guia, entre em contato com o proprietário da equipe para obter assistência.

No momento, estamos trabalhando em uma correção para equipes futuras criadas com base em modelos personalizados.

**Problema**: ao usar Teams no navegador, alguns sites não dão suporte a serem renderizados em uma Teams guia.

![mensagem de erro do navegador.](media/browser-error-message.png)

**Solução**: se você tiver problemas para exibir o conteúdo da guia do site, será redirecionado para abrir a guia em uma página da Web separada ou abrir o Teams no aplicativo da área de trabalho para exibir seu aplicativo de guia do site.

## <a name="related-topics"></a>Tópicos relacionados

- [Introdução com modelos de equipe no centro de administração](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar um modelo de uma equipe existente](create-template-from-existing-team.md)
- [Criar um modelo de equipe com base em um modelo de equipe existente](create-template-from-existing-template.md)
