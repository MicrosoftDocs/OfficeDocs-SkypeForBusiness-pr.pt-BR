---
title: Configuração de reunião criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Elas não se aplicam à reuniões ad-hoc criadas clicando na opção Reunir Agora no cliente.
ms.openlocfilehash: 6af03588f5265c7fba208e88f2965639a1933153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910887"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuração da Reunião: Criar Nova ou Editar Existente

As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Elas não se aplicam a reuniões ad-hoc criadas clicando na opção **Reunir Agora** no cliente.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Escopo** Identifica o escopo da configuração de reunião que você está criando ou modificando: global, site ou pool.

- **Nome** As configurações de reunião são nomeadas por padrão e o nome não pode ser alterado.

- **Os chamadores da PSTN bypass lobby** Marque esta caixa de seleção admitir automaticamente os usuários que estão discando para a conferência através de uma linha de telefone telefônica pública comutada (PSTN) de rede. Desmarque essa caixa de seleção para encaminhar os chamadores PSTN ao lobby de conferência, no qual esperam até que um apresentador da conferência conceda acesso à conferência.

- **Designar como apresentador** Selecione a categoria de usuários (além do organizador da reunião), que são automaticamente designados como apresentadores quando eles ingressam em uma conferência. Independentemente dessa configuração, os apresentadores podem ser explicitamente designados como apresentadores quando a conferência é agendada ou podem ser explicitamente promovidos a apresentadores durante a conferência. As opções são:

  - **Nenhum** Selecione essa opção se ninguém exceto o organizador for designado automaticamente como um apresentador.

  - **Empresa** Selecione esta opção para designar automaticamente somente membros de sua organização como apresentadores.

  - **Todos** Selecione esta opção para designar automaticamente qualquer pessoa seja um apresentador.

- **Tipo de conferência atribuído por padrão** Essa configuração controla se o suplemento de conferência do Outlook sempre agenda conferências por meio do organizador atribuído a conferência, que significa que agendadas conferências sempre têm a mesma URL de ingresso e informações de áudio. Marque essa caixa de seleção para que as conferências agendadas sempre usem a mesma URL de participação. Desmarque essa caixa de seleção para usar uma URL de participação diferente para cada conferência.

- **Usuários anônimos admitir por padrão** Marque esta caixa de seleção se anônimos (ou seja, não autenticado) os usuários poderão participar de conferências por padrão. Desmarque essa caixa de seleção se os usuários anônimos não tiverem permissão de participar de conferências por padrão.

- **URL do logotipo** Digite a URL que tem a imagem a ser usada para convites personalizadas da conferência.

- **URL da Ajuda** Digite a URL de um site onde os usuários podem obter assistência para ingressar na conferência.

- **URL do texto legal** Digite a URL de um site que tenha informações jurídicas e avisos de isenção para a conferência.

- **Texto do rodapé personalizado** Digite o texto a ser usado em convites de reunião personalizados.

Para obter detalhes sobre como trabalhar com configurações de reunião, consulte [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) na documentação Operações. Para obter detalhes sobre como definir as configurações de reunião para reuniões de grande porte, consulte  [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) na documentação Planejamento.


