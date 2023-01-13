---
title: Planos de fundo de reunião personalizados para reuniões do Teams
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: Usando ativos corporativos aprovados, como planos de fundo, para criar planos de fundo personalizados para reuniões do Teams em sua organização.
ms.openlocfilehash: f274165a24db2988cb95ad5900220168d0d60fdc
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800225"
---
# <a name="custom-meeting-backgrounds-for-teams-meetings"></a>Planos de fundo de reunião personalizados para reuniões do Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

## <a name="overview"></a>Visão geral

A personalização em reuniões do Teams permite que as organizações estendam suas identidades visuais pela experiência da reunião. O uso de planos de fundo de reunião personalizados ajuda a promover a criação de cultura corporativa interna e aumentar a conscientização geral da marca com os participantes da reunião interna e externa. Com a ajuda das equipes de gerenciamento de marca e comunicação corporativa de uma organização, os administradores podem facilmente configurar e criar planos de fundo de reunião personalizados para várias unidades de negócios e departamentos dentro de um único locatário.

Por padrão, os usuários licenciados premium do Teams que são administradores ou receberam uma política de personalização de reunião podem criar reuniões que apresentam planos de fundo de reunião personalizados. Essas origens personalizadas só estarão disponíveis para usuários finais em sua organização que têm uma licença de Teams Premium a ser usada.

## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar planos de fundo de reunião personalizados para suas Reuniões do Teams, verifique se você tem os seguintes itens:

- Acesso ao SKU Teams Premium
- Você é um administrador com acesso ao centro de administração do Teams ou recebeu uma política de personalização
- Você habilitou a [política de plano de fundo personalizada](#enabling-the-custom-background-policy)
- Suas imagens em segundo plano atendem às [especificações necessárias](#adding-custom-background-images)

## <a name="setting-up-custom-meeting-backgrounds"></a>Configurando planos de fundo de reunião personalizados

Os administradores podem carregar e gerenciar planos de fundo de reunião personalizados para reuniões do Teams no centro de administração do Teams.

### <a name="enabling-the-custom-background-policy"></a>Habilitando a política de plano de fundo personalizada

Como administrador, para criar planos de fundo personalizados, você precisará criar uma nova política de personalização de reunião ou modificar a política padrão global organizacional.
Para habilitar a política de plano de fundo personalizada, os administradores executarão as seguintes etapas:

1. Abrir o centro de administração do Teams
2. Selecione **Reuniões** no painel de navegação
3. Em Reuniões, há duas maneiras de acessar a política de plano de fundo personalizada. Você pode selecionar **Políticas de Personalização** para selecionar uma política existente ou criar uma nova. Como alternativa, você pode selecionar **Políticas de Reunião** e, em seguida, selecionar o botão **Imagens de reunião personalizadas** no canto superior direito.
4. Na política escolhida, navegue até a seção **Planos de Fundo de Reunião Personalizados**
5. Alternar a configuração de **planos de fundo personalizados** de desativada para ativar para habilitar a configuração
6. Selecione **Salvar**

### <a name="adding-custom-background-images"></a>Adicionando imagens personalizadas em segundo plano

Agora que você habilitou a política de plano de fundo personalizada, você pode carregar suas imagens personalizadas em segundo plano. Essas imagens serão exibidas nas interfaces dos usuários finais, ordenadas até o momento do upload.

Os uploads devem seguir os parâmetros a seguir. Os administradores podem carregar:

- Formatos de imagem PNG e JPEG para suas imagens
- Imagens com dimensões mínimas de 360 px X 360 px
- Imagens com dimensões mínimas de 3840 px X 2160 px
- Um máximo de 50 imagens personalizadas em segundo plano

Para carregar suas imagens, navegue até **Políticas de Personalização** de **Reuniões** >  e selecione sua política na etapa anterior. Role para baixo até a seção **Planos de fundo de reunião personalizados** e, sob a tabela com o alternância de plano de fundo personalizado, selecione **+Adicionar**. Depois de selecionar +Adicionar, um painel chamado **Gerenciamento de Planos de Fundo** será aberto, permitindo que você adicione suas imagens.

> [!NOTE]
> Somente usuários finais com uma licença de Teams Premium verão essas imagens no painel Configurações em Segundo Plano.

### <a name="saving-custom-background-images"></a>Salvando imagens personalizadas em segundo plano

Você encontrará visualizações de suas imagens carregadas em uma nova tabela na seção **Planos de fundo de reunião personalizados** . Esta tabela também exibe o nome e a resolução de suas imagens. Depois de confirmar sua escolha de imagens carregadas, selecione o botão **Salvar** abaixo da tabela de visualização. Agora que você selecionou salvar, seus planos de fundo carregados estão visíveis para seus usuários finais com uma licença Teams Premium.

## <a name="where-are-custom-backgrounds-visible"></a>Onde estão visíveis os planos de fundo personalizados

A lista a seguir exibe clientes com suporte em que os planos de fundo personalizados estão visíveis:

- Clientes Web
- Cliente de desktop
- Android
- iOS

### <a name="who-can-select-and-apply-custom-meeting-backgrounds"></a>Quem pode selecionar e aplicar planos de fundo de reunião personalizados

Somente Teams Premium usuários licenciados podem usar os planos de fundo da reunião no painel Configurações em Segundo Plano.

> [!NOTE]
> Usuários externos ou anônimos não podem usar planos de fundo de reunião personalizados.

### <a name="who-can-view-custom-meeting-backgrounds"></a>Quem pode exibir planos de fundo de reunião personalizados

Embora apenas usuários finais licenciados possam selecionar sua escolha de planos de fundo carregados, qualquer pessoa pode exibir o plano de fundo aplicado a uma reunião. Esses usuários incluem:

- In-tenant, Teams Premium usuários licenciados
- Usuários in-tenant e não licenciados
- Usuários Externos
- Usuários anônimos
