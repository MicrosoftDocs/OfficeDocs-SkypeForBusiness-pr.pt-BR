---
title: Configuração da Reunião Criar Novo ou Editar Existente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Eles não se aplicam a reuniões ad hoc criadas clicando na opção Reunir Agora no cliente.
---

# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuração de Reunião: Criar Novo ou Editar Existente

As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Eles não se aplicam a reuniões ad hoc criadas clicando na opção **Reunir Agora** no cliente.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Escopo** Identifica o escopo da configuração de reunião que você está criando ou modificando: global, site ou pool.

- **Nome** As configurações de reunião são nomeadas por padrão e o nome não pode ser alterado.

- **Chamadores PSTN ignoram lobby** Marque essa caixa de seleção para admitir automaticamente os usuários que estão discando na conferência por meio de uma linha telefônica PSTN (rede telefônica pública comutado). Desmarque essa caixa de seleção para encaminhar os chamadores PSTN ao lobby de conferência, no qual esperam até que um apresentar da conferência conceda acesso à conferência.

- **Designar como apresentador** Selecione a categoria de usuários (além do organizador da reunião) que são automaticamente designados como apresentadores quando inserem em uma conferência. Independentemente dessa configuração, os apresentadores podem ser explicitamente designados como apresentadores quando a conferência é agendada ou podem ser explicitamente promovidos a apresentadores durante a conferência. As opções são:

  - **Nenhum** Selecione essa opção se ninguém além do organizador for designado automaticamente como apresentador.

  - **Empresa** Selecione essa opção para designar automaticamente somente membros da sua organização como apresentadores.

  - **Todos** Selecione essa opção para designar automaticamente qualquer pessoa para ser apresentador.

- **Tipo de conferência atribuído por padrão** Essa configuração controla se o Outlook de Conferência sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as conferências agendadas sempre têm a mesma URL de junção e informações de áudio. Marque essa caixa de seleção para que as conferências agendadas sempre usem o mesmo URL de ingresso. Desmarque essa caixa de seleção para usar URL de ingresso diferente para cada conferência.

- **Admitir usuários anônimos por padrão** Marque essa caixa de seleção se usuários anônimos (ou seja, não autenticados) podem participar de conferências por padrão. Desmarque essa caixa de seleção se os usuários anônimos não tiverem permissão de participar de conferências por padrão.

- **URL de logotipo** Digite a URL que tem a imagem a ser usada para convites de conferência personalizados.

- **URL da Ajuda** Digite a URL de um site onde os usuários podem obter assistência para ingressar na conferência.

- **URL de texto legal** Digite a URL de um site que tenha as informações legais e avisos de isenção de responsabilidade para a conferência.

- **Texto do rodapé personalizado** Digite o texto a ser usado em convites de conferência personalizados.

Para obter detalhes sobre como trabalhar com configurações de reunião, consulte [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) na documentação Operações. Para obter detalhes sobre como definir as configurações de reunião para reuniões de grande porte, consulte [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) na documentação Planejamento.