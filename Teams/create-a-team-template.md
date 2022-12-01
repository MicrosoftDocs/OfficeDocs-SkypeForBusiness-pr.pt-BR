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
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c99fc2ebedac1372beff283ccbcf057c0bfdf78b
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198513"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Criar um modelo de equipe personalizado no Microsoft Teams

**Ainda não há suporte para modelos personalizados para clientes EDU.**

Um modelo de equipe personalizado é uma estrutura de equipe predefinida com um conjunto de canais, guias e aplicativos. Você pode desenvolver um modelo que ajuda a criar o espaço de colaboração certo rapidamente. Seu modelo de equipe personalizado usa suas configurações preferidas.  

<br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4P5rx]


Para começar:

1. Entre no Centro de administração do Teams.

2. Na navegação à esquerda, **expanda****modelos do Teams** >  Team.

3. Selecione **Adicionar**.

    ![Uma imagem da caixa de diálogo Modelos da Equipe com Adicionar realçado.](media/team-templates-new.png)

4. Na seção **Modelos de equipe** , selecione **Criar um novo modelo**.

5. Na seção **Configurações de modelo** , conclua os seguintes campos e selecione **Avançar**:
    - Nome do modelo
    - Descrições curtas e longas do modelo
    - Visibilidade da localidade  

    ![Uma imagem da caixa de diálogo de nomenclatura de configurações de modelos da Equipe.](media/template-add-a-name.png)

6. Na seção **canais, guias e aplicativos** , adicione todos os canais e aplicativos necessários à sua equipe.

    1. Na seção **Canais** , selecione **Adicionar**.
    2. Na caixa **de diálogo Adicionar** , nomeie o canal.
    3. Adicione uma descrição.
    4. Decida se o canal deve ser mostrado por padrão.
    5. Pesquise um nome de aplicativo que você deseja adicionar ao canal.
    6. Selecione **Aplicar** quando terminar.

    ![Uma imagem da tela canais, guias e aplicativos de modelos da Equipe.](media/template-channels-tabs-apps.png)

8. Selecione **Enviar** quando concluído.

Seu novo modelo é exibido na lista **de modelos da Equipe** . O modelo pode ser usado para criar uma equipe no Teams.

> [!Note]
> Pode levar até 24 horas para que os usuários do teams vejam uma alteração de modelo personalizada na galeria.

## <a name="customizing-website-tab-apps"></a>Personalizando aplicativos da Guia do Site

> [!Note]
> Esse recurso está em versão prévia

Talvez você queira especificar URLs para guias de site para canais em modelos de equipe personalizados. Os usuários finais que criarem equipes com modelos terão guias de site predefinidas para a URL do site especificada.

Para começar:

1. Crie um novo modelo de equipe ou edite um modelo de equipe existente.

2. Na seção Canais, adicione um novo canal ou selecione um canal existente e selecione **Editar**.

3. Na seção **Adicionar um aplicativo para este modelo** , adicione um aplicativo Site.

    ![adicionar um aplicativo para essa opção de modelo.](media/add-an-app-template.png)

4. Selecione o ícone de edição e insira a URL de sua escolha.

    ![adicionar uma url de aplicativo.](media/add-url-app-template.png)

5. Selecione **Salvar** para suas edições de aplicativo de guia e selecione **Aplicar** para salvar suas alterações.

## <a name="known-issues"></a>Problemas conhecidos

**Problema**: se você criou uma equipe a partir de um modelo personalizado que continha guias personalizadas adicionais, você poderá ver guias em branco no lugar de seus aplicativos de guia personalizados. As guias padrão (como **Postagens**, **Arquivos** e **Wiki**) serão exibidas conforme o esperado.

**Solução**: para corrigir esse problema, remova a guia personalizada e adicione uma nova guia com o mesmo aplicativo. Se você não tiver permissões para remover a guia personalizada e adicionar uma nova guia, entre em contato com o proprietário da equipe para obter assistência.

No momento, estamos trabalhando em uma correção para futuras equipes criadas a partir de modelos personalizados.

**Problema**: ao usar o Teams no navegador, alguns sites não dão suporte a ser renderizados em uma guia do Teams.

![mensagem de erro do navegador.](media/browser-error-message.png)

**Solução**: se você tiver problemas para exibir o conteúdo da guia do site, será redirecionado para abrir a guia em uma página da Web separada ou abrir o Teams no aplicativo da área de trabalho para exibir o aplicativo de guia do site.

## <a name="related-topics"></a>Tópicos relacionados

- [Introdução aos modelos de equipe no centro de administração](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar um modelo de uma equipe existente](create-template-from-existing-team.md)
- [Criar um modelo de equipe a partir de um modelo de equipe existente](create-template-from-existing-template.md)
