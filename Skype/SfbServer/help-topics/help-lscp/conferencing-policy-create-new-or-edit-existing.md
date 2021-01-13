---
title: Política de Conferência Criar Nova ou Editar Existente
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
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: Uma política de conferência define os recursos e capacidades que os usuários têm disponíveis durante uma conferência (também conhecida como reunião).
ms.openlocfilehash: bd4a813bf8b46c9c8dade72318cb003fb97f2a96
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807451"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a>Política de Conferência: Criar Novo ou Editar Existente

Uma política de conferência define os recursos e capacidades que os usuários têm disponíveis durante uma conferência (também conhecida como reunião).

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Escopo** Identifica o escopo da política de conferência que você está criando ou modificando: global, site ou usuário.

- **Nome** Cada política de conferência exige um nome. As políticas de conferência global e site têm um nome por padrão, e não é possível alterá-lo. Para políticas de conferência do usuário, use um nome descritivo que identifique o usuário ou grupo de usuários.

    > [!NOTE]
    > Depois de salvar a política de conferência, o nome não pode ser alterado.

- **Descrição** Esse campo é opcional. Use-o para fornecer detalhes adicionais sobre a política de conferência.

- **Política do organizador** As configurações nesta seção se aplicam ao usuário que organiza uma conferência. Se uma configuração for selecionada, o usuário poderá organizar uma conferência que tenha a característica especificada. Se uma configuração não for selecionada, o usuário não poderá organizar uma conferência com essa característica. Essa configurações não determinam a que o usuário tem acesso como participante de outras conferências.

    Clique na seta para cima ou para baixo ao lado do rótulo para fechar ou abrir a seção.

- **Tamanho máximo da** reunião do número máximo de usuários permitidos em uma conferência. Por padrão, o tamanho máximo da conferência é de 250.

- **Permitir que os participantes convidem usuários anônimos** Marque essa caixa de seleção para permitir que os usuários convidem usuários anônimos para conferências. Usuários anônimos são usuários que não têm credenciais nos Serviços de Domínio Active Directory da sua organização e que, portanto, não são autenticados.

- **Gravação** Especifique se os participantes podem gravar conferências. As opções são **Nenhum** ou **Habilitar gravação**.

- **Permitir que participantes federados e anônimos gravem** Marque essa caixa de seleção para permitir que participantes externos e não autenticados gravem conferências.

- **Áudio/vídeo** Especifique se os participantes podem usar áudio e vídeo:

  - **Nenhum** Selecione essa opção para impedir o uso de áudio e vídeo.

  - **Habilitar áudio IP** Selecione essa opção para permitir o uso de áudio, mas não de vídeo.

  - **Habilitar áudio/vídeo IP** Selecione essa opção para permitir áudio e vídeo.

- **Habilitar conferência discado PSTN** Se você habilitar o áudio em **Áudio/Vídeo,** marque essa caixa de seleção para permitir que os usuários disquem para conferências usando a rede telefônica pública comutado (PSTN).

- **Permitir que participantes anônimos disem** Marque essa caixa de seleção se você permitir que os usuários disquem para conferências e quiser permitir que usuários não autenticados (anônimos) participem de uma conferência usando a discagem de saída. Com a telefonia de discagem, o servidor de conferência chama o usuário e o usuário atende ao telefone para ingressar na conferência.

- **Permitir que participantes não habilitados para Enterprise Voice disque** Se você habilitar o áudio em **áudio/vídeo,** marque essa caixa de seleção para permitir que os usuários que não estão habilitados para o Enterprise Voice participem de uma conferência usando a discagem de saída. Com a telefonia de discagem, o servidor de conferência liga para o usuário e o usuário atende ao telefone para ingressar na conferência.

- **Permitir vários fluxos de vídeo** Se você habilitar o vídeo em **Áudio/Vídeo,** marque essa caixa de seleção para permitir que os usuários organizem conferências com o vídeo do Modo de Exibição de Galeria. Quando essa caixa de seleção é marcada, os usuários podem organizar conferências que enviam múltiplos fluxos de vídeo. Quando essa caixa de seleção não é marcada, os usuário podem apenas organizar conferências que enviam um único fluxo de vídeo.

    > [!NOTE]
    > Essa opção determina o tipo de fluxo de vídeo suportado pela conferência. Não determina se os participantes podem receber múltiplos fluxos de vídeo. A opção **Permitir que os participantes ingressem com múltiplos fluxos de vídeo** determina se os participantes podem receber múltiplos fluxos de vídeo.

- **Colaboração de dados** Especifica se a conferência permite ou não a colaboração de dados. As opções são **Nenhum** ou **Habilitar colaboração de dados**.

    As configurações a seguir se aplicam à colaboração de dados:

  - **Permitir que participantes federados e anônimos baixem conteúdo** Se você permitir a colaboração de dados, marque essa caixa de seleção para permitir que usuários externos e não autenticados baixem conteúdo, como slides ou apostilas, de uma conferência.

  - **Permitir que os participantes transfira arquivos** Se você permitir a colaboração de dados, marque essa caixa de seleção para permitir transferências de arquivos para todos os participantes durante uma conferência.

  - **Habilitar anotações** Se você permitir a colaboração de dados, marque essa caixa de seleção para permitir que os participantes façam anotações na tela sobre o conteúdo compartilhado durante a conferência.

  - **Habilitar anotações do PowerPoint** Se você permitir a anotação, marque essa caixa de seleção para permitir que os participantes façam anotações em slides do PowerPoint compartilhados durante a conferência.

  - **Habilitar votações** Se você permitir a colaboração de dados, marque essa caixa de seleção para permitir que os participantes realizarem uma sondagem durante uma conferência.

- **Compartilhamento de aplicativos** Especifica se a conferência permite ou não o compartilhamento de aplicativos. As opções são **Desabilitar compartilhamento de aplicativos** ou **Habilitar compartilhamento de aplicativos**.

    As configurações a seguir se aplicam ao compartilhamento de aplicativo:

  - **Permitir que os participantes controlem** Se você permitir o compartilhamento de aplicativos, marque essa caixa de seleção para permitir que os participantes controlem os aplicativos ou áreas de trabalho compartilhados durante a conferência.

  - **Permitir que os participantes federados e anônimos assumirem o controle** Se você permitir o compartilhamento de aplicativos, marque essa caixa de seleção para permitir que participantes externos e não autenticados controlem aplicativos ou áreas de trabalho compartilhados durante a conferência.

- **Política do participante** As configurações nesta seção se aplicam aos usuários como participantes em uma conferência ou sessão de duas partes. Como as configurações a seguir são realizadas de acordo com o usuário, um usuário em uma conferência ou sessão de duas partes pode ter recursos diferentes do que outro usuário na mesma conferência ou sessão de duas partes.

    Clique na seta para cima ou para baixo ao lado do rótulo para fechar ou abrir a seção.

- Selecione **Habilitar compartilhamento de área de trabalho e aplicativos** para permitir que os usuários compartilhem aplicativos ou suas áreas de trabalho enquanto participam de uma conferência ou sessão de duas partes. Selecione **Desabilitar compartilhamento de área de trabalho e aplicativos** para impedir que os usuários compartilhem aplicativos ou suas áreas de trabalho enquanto participam de uma conferência ou sessão de duas partes.

- **Habilitar a transferência de arquivos ponto a ponto** Marque essa caixa de seleção para permitir transferências de arquivo de pessoa para pessoa (ou seja, transferências de arquivo que não envolvem todos os participantes) durante uma conferência ou sessão de duas partes.

- **Habilitar a gravação ponto a ponto** Marque essa caixa de seleção para permitir que os usuários gravem sessões de duas partes.

- **Permitir que os participantes participem com vários fluxos de vídeo** Marque essa caixa de seleção para permitir que os participantes recebam vídeo do Gallery View em conferências que permitem isso. Se essa opção não for selecionada, os participantes poderão receber apenas um único fluxo de vídeo independentemente do que a conferência permite.

    > [!NOTE]
    > **Permitir múltiplos fluxos de vídeo** determina se uma conferência permite múltiplos fluxos de vídeo.

Para obter detalhes sobre recursos de conferência, consulte [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) na documentação Planejamento. Para obter detalhes sobre como trabalhar com políticas de conferência, consulte [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) na documentação Operações.


