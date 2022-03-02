---
title: Personalizar seus aplicativos Teams com base na licença
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como fixar Teams aplicativos para usuários em sua organização com base na licença.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d9c316c042230237089d57c23156cf6ac5284c6
ms.sourcegitcommit: 5b1d8d6f811fab0b350a09e5187d982f952d0edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2022
ms.locfileid: "63047191"
---
# <a name="tailor-your-teams-apps-based-on-license"></a>Personalizar seus aplicativos Teams com base na licença

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

> [!NOTE]
> Atualmente, esse recurso se aplica às licenças F. Portanto, este artigo se concentra na experiência de trabalho de linha de frente. Outros tipos de licença terão suporte no futuro.

## <a name="overview"></a>Visão Geral

Teams fornece uma maneira de fixar aplicativos com base na licença. Quando um usuário entra para Teams com a experiência de aplicativo personalizada habilitada, o usuário obtém uma experiência de aplicativo personalizada com base em sua licença.

Esse recurso fornece aos usuários os aplicativos mais relevantes Teams sem qualquer ação necessária do administrador.

## <a name="tailored-app-experience"></a>Experiência de aplicativo personalizada

Os aplicativos são fixados na barra de aplicativos, que é a barra no lado do cliente da área de trabalho Teams e na parte inferior dos clientes móveis do Teams (iOS e Android).

Aplicativos fixados para usuários que têm uma licença F:

- Conexões do Microsoft Viva
- Atividade
- Bate-papo
- Teams
- Walkie Talkie
- Tarefas
- Turnos
- Aprovações

## <a name="admin-controls"></a>Controles de administrador

> [!NOTE]
> O pinamento do usuário deve estar ligado na política de configuração de aplicativo global (padrão em toda a [organização) para](teams-app-setup-policies.md) que esse recurso entre em vigor.

O recurso de experiência de aplicativo personalizado é controlado pela configuração Mostrar **aplicativos personalizados** com base nas licenças do aplicativo em [](manage-apps.md#manage-org-wide-app-settings) toda a organização na página Gerenciar aplicativos do centro de administração Teams. Se o recurso estiver em funcionamento, todos os usuários da sua organização que têm uma licença F obterão a experiência de aplicativo personalizada.

Tenha em mente que quaisquer políticas de configuração de aplicativo personalizadas atribuídas aos usuários têm precedência. Isso significa que, se um usuário já tiver uma política de configuração de aplicativo personalizada atribuída a ele, o usuário obtém a configuração definida na política de configuração de aplicativo personalizada. Para saber mais sobre como o recurso funciona com políticas de configuração de aplicativos existentes que você aplicou em sua organização, consulte a seção [Cenários](#scenarios) deste artigo.

Esse recurso está habilitado por padrão. No entanto, se você não quiser a experiência de aplicativo personalizada fornecida pela Microsoft, poderá desativar o recurso. Para desativar ou ativar o recurso:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Teams **appsManage** >  e selecione **Configurações de** aplicativos em toda a organização.
2. Em **Aplicativos personalizados**, alterne **a opção Mostrar aplicativos personalizados com base em licenças** alternando para **Off** ou **On**.

## <a name="scenarios"></a>Cenários

Use as informações nesta tabela para saber como o recurso de experiência de aplicativo personalizado funciona em vários cenários, incluindo quando você aplicou políticas de configuração de aplicativos existentes.

|Se...  |Em seguida, ... |
|---------|---------|
|Um usuário tem a política de configuração de aplicativo global e o recurso está em.     | O usuário obtém a experiência de aplicativo personalizada. Os aplicativos definidos na política de configuração de aplicativo global ainda estão fixados e aparecem mais abaixo na lista de aplicativos fixados.      |
|Um usuário tem uma política de configuração de aplicativo personalizada e o recurso está em.    |O usuário obtém a configuração definida na política de configuração de aplicativo personalizada.          |
|O recurso está em e você atualiza a política de configuração de aplicativo global.     |O usuário obtém a experiência de aplicativo personalizada com base em sua licença. Os aplicativos definidos na política de configuração de aplicativo global ainda estão fixados e aparecem mais abaixo na lista de aplicativos fixados.          |
|O recurso está desligado.   | O usuário obtém a experiência definida na política de configuração de aplicativo global ou na política de configuração de aplicativo personalizada atribuída a eles.          |
|Um usuário tem uma licença E, A ou G e o recurso está em.   | O usuário não tem a experiência de aplicativo personalizada. Atualmente, a experiência do aplicativo personalizado se aplica somente aos usuários que têm uma licença F.        |
|Um aplicativo na experiência de aplicativo personalizado é bloqueado para um usuário ou para sua organização.      |A experiência do aplicativo personalizado honra a política de permissão do aplicativo. Se um aplicativo for bloqueado, os usuários não verão o aplicativo bloqueado.           |
|Um aplicativo na experiência de aplicativo personalizado já está definido em uma política de configuração de aplicativo e o recurso está em. |O aplicativo é fixado com base na ordem definida pela experiência do aplicativo personalizado.        |

> [!NOTE]
> Não é possível alterar os aplicativos ou a ordem dos aplicativos na experiência do aplicativo personalizado. Por enquanto, se você quiser fazer alterações, poderá configurar sua própria experiência personalizada. Para fazer isso, primeiro desligue o recurso. Em seguida, [crie uma política de configuração de aplicativo personalizada](teams-app-setup-policies.md) e [atribua-a a usuários ou grupos](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
