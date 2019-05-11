---
title: Política de conferência criar nova ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: A política de conferência define os recursos e capacidades disponíveis aos usuários durante uma conferência (também conhecida como reunião).
ms.openlocfilehash: a1d44b78efe93f554fcf0e36dca0ebb2bf914b47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929179"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Política de Conferência: Criar Nova ou Editar Existente

A política de conferência define os recursos e capacidades disponíveis aos usuários durante uma conferência (também conhecida como reunião).

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Escopo** Identifica o escopo da política de conferência que você está criando ou modificando: global, site ou usuário.

- **Nome** Cada política de conferência requer um nome. As políticas de conferência global e site têm um nome por padrão, e não é possível alterá-lo. Para políticas de conferência do usuário, use um nome descritivo que identifique o usuário ou grupo de usuários.

    > [!NOTE]
    > Depois de salvar a política de conferência, o nome não pode ser alterado.

- **Descrição** Este campo é opcional. Use-o para fornecer detalhes adicionais sobre a política de conferência.

- **Política de organizador** As configurações desta seção se aplicam ao usuário que organiza uma conferência. Se uma configuração for selecionada, o usuário poderá organizar uma conferência que tenha a característica especificada. Se uma configuração não for selecionada, o usuário não poderá organizar uma conferência com essa característica. Essa configurações não determinam a que o usuário tem acesso como participante de outras conferências.

    Clique na seta para cima ou para baixo ao lado do rótulo para fechar ou abrir a seção.

- **Tamanho máximo de reunião** o número máximo de usuários que são permitidas em uma conferência. Por padrão, o tamanho máximo de conferência é 250.

- **Permitir que os participantes convidem usuários anônimos** Marque esta caixa de seleção para permitir que usuários convidem usuários anônimos para conferências. Usuários anônimos são usuários que não possuem credenciais nos serviços de domínio de Active Directory da sua organização e que, portanto, não são autenticados.

- **Gravação** Especifique se ou não os participantes podem registrar conferências. As opções são  **Nenhum** ou  **Habilitar gravação**.

- **Permitir federados e os participantes anônimos gravem** Marque essa caixa de seleção para permitir que os participantes externos e não autenticados para conferências de registro.

- **Áudio/vídeo** Especifique se os participantes podem usar áudio e vídeo:

  - **Nenhum** Selecione essa opção para impedir o uso de áudio e vídeo.

  - **Habilitar áudio IP** Selecione essa opção para permitir o uso de áudio, mas não de vídeo.

  - **IP habilitar áudio/vídeo** Selecione essa opção para permitir que o áudio e vídeo.

- **Habilitar PSTN a conferência discada** Se você habilitou o áudio em **áudio/vídeo**, marque essa caixa de seleção para permitir que os usuários disquem para conferências usando a rede telefônica pública comutada (PSTN).

- **Permitir participantes anônimos para fazer uma discagem** Marque esta caixa de seleção se você permitir que os usuários disquem para conferências e deseja permitir que os usuários (anônimos) não-autenticados ingressar em uma conferência usando a discagem externa transmita para. Com a discagem de saída, o servidor de conferência faz uma chamada para o usuário e o usuário atende o telefone para entrar na conferência.

- **Permitir que os participantes não habilitados para o Enterprise Voice fazer uma discagem** Se você habilitou o áudio em **áudio/vídeo**, marque essa caixa de seleção para permitir que os usuários não habilitados para o Enterprise Voice ingressar em uma conferência usando o telefone de discagem externa. Com a telefonia de discagem, o servidor de conferência liga para o usuário e o usuário atende ao telefone para ingressar na conferência.

- **Permitir vários fluxos de vídeo** Se você habilitou o vídeo em **áudio/vídeo**, marque essa caixa de seleção para permitir que usuários organizem webconferências com o vídeo de exibição de galeria. Quando essa caixa de seleção é marcada, os usuários podem organizar conferências que enviam vários fluxos de vídeo. Quando essa caixa de seleção não é marcada, os usuário podem apenas organizar conferências que enviam um único fluxo de vídeo.

    > [!NOTE]
    > Essa opção determina o tipo de fluxo de vídeo suportado pela conferência. Não determina se os participantes podem receber múltiplos fluxos de vídeo. A opção  **Permitir que os participantes ingressem com vários fluxos de vídeo** determina se os participantes podem receber vários fluxos de vídeo.

- **Colaboração de dados** Especifique se ou não a conferência permite a colaboração de dados. As opções são  **Nenhum** ou  **Habilitar colaboração de dados**.

    As configurações a seguir se aplicam à colaboração de dados:

  - **Permitir federados e os participantes anônimos baixem conteúdo** Se você permitir a colaboração de dados, marque esta caixa de seleção para permitir que usuários externos e não autenticados baixem conteúdo, como slides ou folhetos, de uma conferência.

  - **Permitir que os participantes transfiram arquivos** Se você permitir a colaboração de dados, marque esta caixa de seleção para permitir transferências de arquivo para todos os participantes durante uma conferência.

  - **Habilitar anotações** Se você permitir a colaboração de dados, marque essa caixa de seleção para permitir que os participantes façam na tela anotações no conteúdo compartilhado durante a conferência.

  - **PowerPoint habilitar anotações** Se você permitir a anotação, marque essa caixa de seleção para permitir que os participantes façam anotações em slides do PowerPoint compartilhados durante a conferência.

  - **Habilitar sondagens** Se você permitir a colaboração de dados, marque essa caixa de seleção para permitir que os participantes realizem sondagens durante uma conferência.

- **Compartilhamento de aplicativos** Especifique se ou não a conferência permite o compartilhamento de aplicativo. As opções são **Desabilitar compartilhamento de aplicativos** ou  **Habilitar compartilhamento de aplicativos**.

    As configurações a seguir se aplicam ao compartilhamento de aplicativos:

  - **Permitir que os participantes assumam o controle** Se você permitir o compartilhamento de aplicativos, marque essa caixa de seleção para permitir que os participantes assumam o controle de aplicativos ou áreas de trabalho que são compartilhadas durante a conferência.

  - **Permitir federados e participantes anônimos assumam o controle** Se você permitir o compartilhamento de aplicativos, marque essa caixa de seleção para permitir que os participantes externos e não autenticados assumam o controle de aplicativos ou áreas de trabalho que são compartilhadas durante a conferência.

- **Política do participante** As configurações desta seção se aplicam aos usuários como participantes em uma conferência ou sessão de duas partes. Como as configurações a seguir são realizadas de acordo com o usuário, um usuário em uma conferência ou sessão de duas partes pode ter recursos diferentes do que outro usuário na mesma conferência ou sessão de duas partes.

    Clique na seta para cima ou para baixo ao lado do rótulo para fechar ou abrir a seção.

- Selecione  **Habilitar compartilhamento de área de trabalho e aplicativos** para permitir que os usuários compartilhem aplicativos ou suas áreas de trabalho enquanto participam de uma conferência ou sessão de duas partes. Selecione  **Desabilitar compartilhamento de área de trabalho e aplicativos** para impedir que os usuários compartilhem aplicativos ou suas áreas de trabalho enquanto participam de uma conferência ou sessão de duas partes.

- **Habilitar a transferência de arquivos ponto a ponto** Marque esta caixa de seleção para permitir transferências de arquivo de pessoa para pessoa (ou seja, transferências de arquivo que não envolvem todos os participantes) durante uma conferência ou sessão de duas partes.

- **Habilitar a gravação ponto a ponto** Marque esta caixa de seleção para permitir que os usuários gravem sessões de duas partes.

- **Permitir que os participantes ingressem com vários fluxos de vídeos** Marque essa caixa de seleção para permitir que os participantes receber o modo de exibição de galeria vídeo em conferências que a permitem. Se essa opção não for selecionada, os participantes poderão receber apenas um único fluxo de vídeo independentemente do que a conferência permite.

    > [!NOTE]
    > **Permitir vários fluxos de vídeo** determina se uma conferência permite vários fluxos de vídeo.

Para obter detalhes sobre recursos de conferência, consulte [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) na documentação Planejamento. Para obter detalhes sobre como trabalhar com políticas de conferência, consulte  [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) na documentação Operações.


