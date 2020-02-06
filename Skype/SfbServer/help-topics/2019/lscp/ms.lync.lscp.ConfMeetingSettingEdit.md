---
title: Configuração da reunião criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Elas não se aplicam à reuniões ad-hoc criadas clicando na opção Reunir Agora no cliente.
ms.openlocfilehash: 7c86415d08d2b48d542334ac74bc1316102e592d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796310"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuração da Reunião: Criar Nova ou Editar Existente

As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Elas não se aplicam a reuniões ad-hoc criadas clicando na opção **Reunir Agora** no cliente.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Escopo** Identifica o escopo da configuração de reunião que você está criando ou modificando: global, site ou pool.

- **Nome** As configurações de reunião são nomeadas por padrão, e o nome não pode ser alterado.

- Os **chamadores PSTN ignoram o lobby** Marque esta caixa de seleção para admitir automaticamente os usuários que estão discando para a conferência por meio de uma linha telefônica PSTN (rede telefônica pública comutada). Desmarque essa caixa de seleção para encaminhar os chamadores PSTN ao lobby de conferência, no qual esperam até que um apresentador da conferência conceda acesso à conferência.

- **Designar como apresentador** Selecione a categoria de usuários (além do organizador da reunião) que são automaticamente designados como apresentadores quando eles ingressam em uma conferência. Independentemente dessa configuração, os apresentadores podem ser explicitamente designados como apresentadores quando a conferência é agendada ou podem ser explicitamente promovidos a apresentadores durante a conferência. As opções são:

  - **Nenhuma delas** Selecione esta opção se ninguém diferente do organizador for automaticamente designado como apresentador.

  - **Empresa** Selecione esta opção para designar automaticamente os membros da sua organização como apresentadores.

  - **Todas as pessoas** Selecione esta opção para designar automaticamente qualquer pessoa para ser um apresentador.

- **Tipo de conferência atribuído por padrão** Esta configuração controla se o suplemento de conferência do Outlook sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as conferências agendadas sempre têm a mesma URL de junção e informações de áudio. Marque essa caixa de seleção para que as conferências agendadas sempre usem a mesma URL de participação. Desmarque essa caixa de seleção para usar uma URL de participação diferente para cada conferência.

- **Admitir usuários anônimos por padrão** Marque esta caixa de seleção se os usuários anônimos (ou seja, não autenticados) tiverem permissão para participar de conferências por padrão. Desmarque essa caixa de seleção se os usuários anônimos não tiverem permissão de participar de conferências por padrão.

- **URL do logotipo** Digite a URL que tem a imagem a ser usada para convites de conferência personalizados.

- **URL da ajuda** Digite a URL de um site em que os usuários podem obter assistência para ingressar na conferência.

- **URL de texto legal** Digite a URL de um site que tenha as informações legais e os avisos de isenção de responsabilidade da conferência.

- **Texto do rodapé personalizado** Digite o texto a ser usado em convites de conferência personalizados.

Para obter detalhes sobre como trabalhar com configurações de reunião, consulte [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) na documentação Operações. Para obter detalhes sobre como definir as configurações de reunião para reuniões de grande porte, consulte  [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) na documentação Planejamento.


