---
title: Criar um modelo de equipe personalizado no Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como criar um modelo de equipe personalizado no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f22b2c53ab6f3c3c90e1720313c135c2106b1a49
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196525"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Criar um modelo de equipe personalizado no Microsoft Teams

**Os modelos personalizados ainda não têm suporte para clientes EDU.**

Um modelo de equipe personalizado é uma estrutura de equipe predefinida com um conjunto de canais, guias e aplicativos. Você pode desenvolver um modelo que o ajude a criar rapidamente o espaço de colaboração certo. Seu modelo de equipe personalizado usa as configurações preferenciais.  

Para começar:

1. Entre no Centro de administração do Teams.

2. No painel de navegação esquerdo, expanda os **modelos de Equipe**  >  **do** Teams.

3. Clique em **Adicionar**.

![Uma imagem da caixa de diálogo Modelos de Equipe com Adicionar realçada.](media/team-templates-new.png)

4. Na seção **Modelos de Equipe,** selecione **Criar um novo modelo.**

5. Na seção **Configurações do modelo,** preencha os seguintes campos e clique em **Próximo:**
    - Nome do modelo
    - Descrições breves e longas do modelo
    - Visibilidade da localidade  

![Uma imagem da caixa de diálogo de nomeação de configurações de modelos de equipe.](media/template-add-a-name.png)

6. Na seção canais, guias e **aplicativos,** adicione todos os canais e aplicativos de que sua equipe precisa.

    1. Na seção **Canais,** clique em **Adicionar.**
    2. Na caixa **de diálogo** Adicionar, nomeia o canal.
    3. Adicione uma descrição.
    4. Decida se o canal deve ser mostrado por padrão.
    5. Pesquise um nome de aplicativo que você deseja adicionar ao canal.
    6. Clique **em Aplicar** quando terminar.

![Uma imagem da tela de modelos de equipe, canais, guias e aplicativos.](media/template-channels-tabs-apps.png)

8. Clique **em Enviar** quando estiver concluído.

Seu novo modelo é exibido na lista **de modelos da** equipe. O modelo pode ser usado para criar uma equipe no Teams.

> [!Note]
> Pode levar até 24 horas para que os usuários das equipes vejam um modelo personalizado na galeria.

## <a name="known-issues"></a>Problemas conhecidos 

**Problema:** se você criou uma equipe a partir de um modelo personalizado que continha guias personalizadas adicionais, talvez você veja guias em branco no lugar dos aplicativos de tabulação personalizados. Suas guias padrão (ou **seja,** **Postagens,** Arquivos e **Wiki)** serão exibidas conforme o esperado.

**Solução:** se você tiver criado uma equipe a partir de um modelo personalizado que continha guias personalizadas adicionais, poderá ver guias em branco no lugar dos aplicativos de tabulação personalizados. Suas guias padrão (ou seja, Postagens, Arquivos e Wiki) serão exibidas conforme o esperado.

Para corrigir esse problema, remova a guia personalizada e adicione uma nova guia com o mesmo aplicativo. Se você não tiver permissões para remover a guia personalizada e adicionar uma nova guia, entre em contato com o proprietário da equipe para pedir que ele faça isso.

Estamos trabalhando em uma correção para equipes futuras criadas a partir de modelos personalizados.

## <a name="related-topics"></a>Tópicos relacionados

- [Começar a usar modelos de equipe no centro de administração](get-started-with-teams-templates-in-the-admin-console.md)
- [Criar um modelo de uma equipe existente](create-template-from-existing-team.md)
- [Criar um modelo de equipe a partir de um modelo de equipe existente](create-template-from-existing-template.md)
