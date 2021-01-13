---
title: Configuração de Reunião Criar Nova ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Elas não se aplicam a reuniões ad-hoc criadas clicando na opção Reunir Agora no cliente.
ms.openlocfilehash: dc37e3d76a81a09fe2cbd2407f4d3a2dff3d703e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803931"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuração de Reunião: Criar Novo ou Editar Existente

As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Elas não se aplicam a reuniões ad-hoc criadas clicando na opção **Reunir Agora** no cliente.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Escopo** Identifica o escopo da configuração de reunião que você está criando ou modificando: global, site ou pool.

- **Nome** As configurações de reunião são nomeadas por padrão e o nome não pode ser alterado.

- **Chamadores PSTN ignoram o lobby** Marque essa caixa de seleção para admitir automaticamente os usuários que estão discando para a conferência por uma linha telefônica PSTN (Rede Telefônica Pública Comutado). Desmarque essa caixa de seleção para encaminhar os chamadores PSTN ao lobby de conferência, no qual esperam até que um apresentar da conferência conceda acesso à conferência.

- **Designar como apresentador** Selecione a categoria de usuários (além do organizador da reunião) que são automaticamente designados como apresentadores ao ingressarem em uma conferência. Independentemente dessa configuração, os apresentadores podem ser explicitamente designados como apresentadores quando a conferência é agendada ou podem ser explicitamente promovidos a apresentadores durante a conferência. As opções são:

  - **Nenhum** Selecione essa opção se ninguém além do organizador for designado automaticamente como apresentador.

  - **Empresa** Selecione essa opção para designar automaticamente somente os membros da sua organização como apresentadores.

  - **Todos** Selecione essa opção para designar automaticamente qualquer pessoa como apresentador.

- **Tipo de conferência atribuído por padrão** Essa configuração controla se o Outlook Conferencing Addin sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as conferências agendadas sempre têm a mesma URL de junção e informações de áudio. Marque essa caixa de seleção para que as conferências agendadas sempre usem o mesmo URL de ingresso. Desmarque essa caixa de seleção para usar URL de ingresso diferente para cada conferência.

- **Admitir usuários anônimos por padrão** Marque essa caixa de seleção se usuários anônimos (ou seja, não autenticados) têm permissão para participar de conferências por padrão. Desmarque essa caixa de seleção se os usuários anônimos não tiverem permissão de participar de conferências por padrão.

- **URL do logotipo** Digite a URL que tem a imagem a ser usada para convites de conferência personalizados.

- **URL da Ajuda** Digite a URL de um site onde os usuários podem obter assistência para ingressar na conferência.

- **URL do texto legal** Digite a URL de um site que tenha as informações legais e avisos de isenção de responsabilidade da conferência.

- **Texto do rodapé personalizado** Digite o texto a ser usado em convites de conferência personalizados.

Para obter detalhes sobre como trabalhar com configurações de reunião, consulte [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) na documentação Operações. Para obter detalhes sobre como definir as configurações de reunião para reuniões de grande porte, consulte [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) na documentação Planejamento.


