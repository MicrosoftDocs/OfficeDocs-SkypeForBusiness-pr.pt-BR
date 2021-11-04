---
title: Política de Conferência Criar Novo ou Editar Existente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: Uma política de conferência define os recursos e recursos que os usuários têm disponíveis durante uma conferência (também conhecida como reunião).
ms.openlocfilehash: 9d62ac561252c3cda025f040c2de335c49c12bae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753010"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Política de Conferência: Criar Novo ou Editar Existente

Uma política de conferência define os recursos e recursos que os usuários têm disponíveis durante uma conferência (também conhecida como reunião).

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Escopo** Identifica o escopo da política de conferência que você está criando ou modificando: global, site ou usuário.

- **Nome** Cada política de conferência requer um nome. As políticas de conferência global e site têm um nome por padrão, e não é possível alterá-lo. Para políticas de conferência do usuário, use um nome descritivo que identifique o usuário ou grupo de usuários.

    > [!NOTE]
    > Depois de salvar a política de conferência, o nome não pode ser alterado.

- **Descrição** Este campo é opcional. Use-o para fornecer detalhes adicionais sobre a política de conferência.

- **Política organizadora** As configurações nesta seção se aplicam ao usuário que organiza uma conferência. Se uma configuração for selecionada, o usuário poderá organizar uma conferência que tenha a característica especificada. Se uma configuração não for selecionada, o usuário não poderá organizar uma conferência com essa característica. Essa configurações não determinam a que o usuário tem acesso como participante de outras conferências.

    Clique na seta para cima ou para baixo ao lado do rótulo para fechar ou abrir a seção.

- **Tamanho máximo da** reunião o número máximo de usuários permitidos em uma conferência. Por padrão, o tamanho máximo da conferência é de 250.

- **Permitir que os participantes convidem usuários anônimos** Marque essa caixa de seleção para permitir que os usuários convidem usuários anônimos para conferências. Os usuários anônimos são usuários que não têm credenciais nos Serviços de Domínio active Directory da sua organização e que, portanto, não são autenticados.

- **Gravação** Especifique se os participantes podem ou não gravar conferências. As opções são **Nenhum** ou **Habilitar gravação**.

- **Permitir que participantes federados e anônimos gravem** Marque essa caixa de seleção para permitir que participantes externos e não autenticados gravem conferências.

- **Áudio/vídeo** Especifique se os participantes podem usar áudio e vídeo:

  - **Nenhum** Selecione essa opção para impedir o uso de áudio e vídeo.

  - **Habilitar áudio IP** Selecione essa opção para permitir o uso de áudio, mas não vídeo.

  - **Habilitar áudio/vídeo IP** Selecione essa opção para permitir áudio e vídeo.

- **Habilitar conferência discagem PSTN** Se você habilitar áudio **em Áudio/vídeo,** marque essa caixa de seleção para permitir que os usuários discem para conferências usando a PSTN (rede telefônica pública comutado).

- **Permitir que participantes anônimos discem** Marque essa caixa de seleção se você permitir que os usuários discem para conferências e você deseja permitir que usuários não autenticados (anônimos) participem de uma conferência usando a discagem discada. Com a telefonia de discagem, o servidor de conferência chama o usuário e o usuário atende ao telefone para ingressar na conferência.

- **Permitir que os participantes não habilitados Enterprise Voice discar** Se você habilitar áudio em **Áudio/vídeo,** marque essa caixa de seleção para permitir que os usuários que não estão habilitados para Enterprise Voice participem de uma conferência usando o fonagem discada. Com a telefonia de discagem, o servidor de conferência liga para o usuário e o usuário atende ao telefone para ingressar na conferência.

- **Permitir vários fluxos de vídeo** Se você habilitar vídeo em **Áudio/vídeo,** marque essa caixa de seleção para permitir que os usuários organizem conferências com o vídeo do Modo de Exibição de Galeria. Quando essa caixa de seleção é marcada, os usuários podem organizar conferências que enviam múltiplos fluxos de vídeo. Quando essa caixa de seleção não é marcada, os usuário podem apenas organizar conferências que enviam um único fluxo de vídeo.

    > [!NOTE]
    > Essa opção determina o tipo de fluxo de vídeo suportado pela conferência. Não determina se os participantes podem receber múltiplos fluxos de vídeo. A opção **Permitir que os participantes ingressem com múltiplos fluxos de vídeo** determina se os participantes podem receber múltiplos fluxos de vídeo.

- **Colaboração de dados** Especifique se a conferência permite ou não a colaboração de dados. As opções são **Nenhum** ou **Habilitar colaboração de dados**.

    As configurações a seguir se aplicam à colaboração de dados:

  - **Permitir que participantes federados e anônimos baixem conteúdo** Se você permitir a colaboração de dados, marque essa caixa de seleção para permitir que usuários externos e não autenticados baixem conteúdo, como slides ou apostilas, de uma conferência.

  - **Permitir que os participantes transfira arquivos** Se você permitir a colaboração de dados, marque essa caixa de seleção para permitir transferências de arquivo para todos os participantes durante uma conferência.

  - **Habilitar anotações** Se você permitir a colaboração de dados, marque essa caixa de seleção para permitir que os participantes façam anotações na tela sobre o conteúdo compartilhado durante a conferência.

  - **Habilitar PowerPoint anotações** Se você permitir anotação, marque essa caixa de seleção para permitir que os participantes façam anotações PowerPoint slides compartilhados durante a conferência.

  - **Habilitar votações** Se você permitir a colaboração de dados, marque essa caixa de seleção para permitir que os participantes realizarem uma sondagem durante uma conferência.

- **Compartilhamento de aplicativos** Especifique se a conferência permite ou não o compartilhamento de aplicativos. As opções são **Desabilitar compartilhamento de aplicativos** ou **Habilitar compartilhamento de aplicativos**.

    As configurações a seguir se aplicam ao compartilhamento de aplicativo:

  - **Permitir que os participantes controlem** Se você permitir o compartilhamento de aplicativos, marque essa caixa de seleção para permitir que os participantes controlem aplicativos ou áreas de trabalho compartilhadas durante a conferência.

  - **Permitir que participantes federados e anônimos controlem** Se você permitir o compartilhamento de aplicativos, marque essa caixa de seleção para permitir que participantes externos e não autenticados controlem aplicativos ou desktops compartilhados durante a conferência.

- **Política de participante** As configurações nesta seção se aplicam aos usuários como participantes em uma conferência ou sessão de duas partes. Como as configurações a seguir são realizadas de acordo com o usuário, um usuário em uma conferência ou sessão de duas partes pode ter recursos diferentes do que outro usuário na mesma conferência ou sessão de duas partes.

    Clique na seta para cima ou para baixo ao lado do rótulo para fechar ou abrir a seção.

- Selecione **Habilitar compartilhamento de área de trabalho e aplicativos** para permitir que os usuários compartilhem aplicativos ou suas áreas de trabalho enquanto participam de uma conferência ou sessão de duas partes. Selecione **Desabilitar compartilhamento de área de trabalho e aplicativos** para impedir que os usuários compartilhem aplicativos ou suas áreas de trabalho enquanto participam de uma conferência ou sessão de duas partes.

- **Habilitar a transferência de arquivos ponto a ponto** Marque essa caixa de seleção para permitir transferências de arquivo de pessoa para pessoa (ou seja, transferências de arquivo que não envolvem todos os participantes) durante uma conferência ou sessão de duas partes.

- **Habilitar a gravação ponto a ponto** Marque essa caixa de seleção para permitir que os usuários gravem sessões de duas partes.

- **Permitir que os participantes participem de vários fluxos de vídeo** Marque essa caixa de seleção para permitir que os participantes recebam vídeo do Gallery View em conferências que o permitem. Se essa opção não for selecionada, os participantes poderão receber apenas um único fluxo de vídeo independentemente do que a conferência permite.

    > [!NOTE]
    > **Permitir múltiplos fluxos de vídeo** determina se uma conferência permite múltiplos fluxos de vídeo.

Para obter detalhes sobre recursos de conferência, consulte [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) na documentação Planejamento. Para obter detalhes sobre como trabalhar com políticas de conferência, consulte [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) na documentação Operações.