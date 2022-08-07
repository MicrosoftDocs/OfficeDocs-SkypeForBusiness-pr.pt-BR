---
title: Gerenciar e filtrar marcas de dispositivo do Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
description: Saiba como gerenciar e filtrar marcas em seus dispositivos do Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a372aacb7a8917dc169855fd671b1382d390f32
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271346"
---
# <a name="manage-microsoft-teams-device-tags"></a>Gerenciar marcas de dispositivo do Microsoft Teams

As marcas de dispositivo no Microsoft Teams permitem agrupar, organizar e gerenciar com mais facilidade os dispositivos implantados em sua organização. Com o Centro de administração do Microsoft Teams, você pode adicionar uma ou mais marcas a dispositivos, usar filtros para exibir dispositivos que correspondem à marca especificada e, em seguida, executar ações nos dispositivos que têm essa marca.

Você pode adicionar uma marca de dispositivo a mais de um tipo de dispositivo. No entanto, quando você abre um painel de dispositivos no centro de administração, somente os dispositivos desse tipo são retornados. Por exemplo, você pode atribuir a marca "Corporativa" a telefones e Salas do Teams dispositivos. Se você pesquisar a marca "Corporativa" enquanto estiver em Telefones de Dispositivos do **Teams** > **, somente** os telefones serão retornados. Da mesma forma, se você pesquisar a marca "Corporativa" em Dispositivos **do Teams** >  **Salas do Teams**, somente Salas do Teams dispositivos serão retornados.

Para gerenciar marcas de dispositivo, você precisa ser um administrador global, administrador do Serviço do Teams ou administrador de Dispositivos do Teams. Para obter mais informações sobre funções de administrador, [consulte Usar funções de administrador do Microsoft Teams para gerenciar o Teams](../using-admin-roles.md).

> [!IMPORTANT]
> As marcas de dispositivo são atribuídas à conta de recurso que está conectada a um dispositivo. Se você assinar uma conta de recurso de um dispositivo e usá-la para entrar em outro dispositivo, as marcas de dispositivo serão aplicadas ao novo dispositivo.

## <a name="create-remove-or-rename-device-tags"></a>Criar, remover ou renomear marcas de dispositivo

Usando o painel de gerenciamento de marca de dispositivo, você pode:

- Veja todas as marcas de dispositivo.
- Crie várias marcas de dispositivo facilmente e atribua-as a dispositivos posteriormente. As marcas podem ter até 25 caracteres.
- Remova as marcas de dispositivo que não são mais necessárias. Antes de remover uma marca de dispositivo, você precisará removê-la de todos os dispositivos aos qual ela foi adicionada.
- Renomeie marcas de dispositivo. Quando você renomeia uma marca de dispositivo, essa alteração é refletida em todos os dispositivos aos qual ela foi adicionada. As marcas podem ter até 25 caracteres.

1. Entre no Centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Navegue **até Dispositivos do Teams** e escolha qualquer painel de dispositivos, como **Telefones**.
3. Selecione **Ações** no canto superior direito da página e selecione **Todas as marcas de dispositivo**.
4. Para criar uma marca de dispositivo, selecione **+ Adicionar**, forneça um valor para a marca do dispositivo e selecione o **ícone** Salvar.
5. Para remover uma marca de dispositivo, selecione as reticências **...** ao lado da marca de dispositivo que você deseja remover e selecione **Excluir**.
    > [!NOTE]
    > Se você tentar remover uma marca de dispositivo que foi adicionada aos dispositivos, receberá uma mensagem perguntando se deseja removê-la de todos os dispositivos. Se você quiser fazer isso e continuar a remover a marca do dispositivo, selecione **Desmarcar dispositivos**.
6. Para renomear uma marca de dispositivo, selecione as reticências **...** ao lado da marca de dispositivo que você deseja renomear e selecione **Editar**. Forneça um novo valor para a marca do dispositivo e selecione o **ícone** Salvar.

## <a name="add-or-remove-tags-on-a-single-device"></a>Adicionar ou remover marcas em um único dispositivo

Ao adicionar marcas a um dispositivo, você pode selecionar uma marca existente ou criar uma nova. As marcas podem ter até 25 caracteres.

1. Entre no Centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Navegue **até Dispositivos do Teams** e escolha o painel de dispositivos que contém o dispositivo no qual você deseja adicionar ou remover marcas.
3. Coloque uma marca de seleção ao lado do dispositivo no qual você deseja adicionar ou remover marcas e selecione **Gerenciar marcas**.
4. Se você quiser adicionar uma marca:
    1. Comece a digitar o nome da marca que você deseja adicionar.
    2. Se a marca já existir, selecione-a na lista de marcas retornadas.
    3. Se a marca não existir, selecione **Adicionar "\<tag name>" como uma nova marca**. As marcas podem ter até 25 caracteres.
5. Se você quiser remover uma marca, selecione **X** ao lado da marca que deseja remover.
6. Repita as etapas acima se quiser adicionar ou remover mais marcas.
7. Selecione **Aplicar**.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Adicionar ou remover marcas em vários dispositivos

Ao adicionar marcas a um dispositivo, você pode selecionar uma marca existente ou criar uma nova. As marcas podem ter até 25 caracteres. Se você quiser remover uma marca de vários dispositivos, precisará selecionar o usuário do Teams associado ao dispositivo e remover a marca do usuário.

1. Entre no Centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Navegue **até Dispositivos do Teams** e escolha o painel de dispositivos que contém os dispositivos nos quais você deseja adicionar ou remover marcas.
3. Coloque uma marca de seleção ao lado dos dispositivos nos quais você deseja adicionar ou remover marcas e selecione **Gerenciar marcas**.
4. Se você quiser adicionar uma marca:
    1. Comece a digitar o nome da marca que você deseja adicionar em Gerenciar **marcas para todos os dispositivos de usuários do Teams**.
    2. Se a marca já existir, selecione-a na lista de marcas retornadas.
    3. Se a marca não existir, selecione **Adicionar "\<tag name>" como uma nova marca**.
5. Se você quiser remover uma marca:
    1. Expanda **Selecionar usuários do Teams**.
    2. Expanda **\<x> as** marcas sob o nome do usuário do Teams do qual você deseja remover marcas.
    3. Selecione **X** ao lado da marca que você deseja remover.
6. Repita as etapas acima se quiser adicionar ou remover mais marcas.
7. Selecione **Aplicar**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Usar filtros para retornar dispositivos com uma marca específica

Se você adicionou marcas de dispositivo aos seus dispositivos, poderá usá-las para filtrar a lista de dispositivos para retornar somente os dispositivos que tiveram uma marca especificada adicionada a eles. Isso pode ser útil se você quiser apenas exibir todos os dispositivos em uma sala específica, todos os dispositivos de um determinado tipo ou qualquer outro critério usado ao adicionar suas marcas. Você também pode executar ações em massa em dispositivos retornados, como aplicar atualizações em ondas ou definir políticas de configuração diferentes, dependendo dos grupos de dispositivos identificados usando marcas de dispositivo.

1. Entre no Centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Navegue **até Dispositivos do Teams** e escolha o painel de dispositivos que contém os dispositivos que você deseja filtrar.
3. Selecione o **ícone Filtro** .
4. Se você quiser especificar apenas uma única marca ou se quiser localizar dispositivos que tenham todas as marcas especificadas, selecione Corresponder a **todas essas condições**.
5. Se você quiser encontrar dispositivos que correspondam a uma ou mais marcas de dispositivo, selecione **Corresponder a qualquer uma dessas condições**.
6. Selecione o **campo Marca** e especifique um nome de marca de dispositivo no **campo Inserir um** valor.
7. Se você quiser adicionar mais marcas de dispositivo, selecione **Adicionar mais** e repita a etapa 6 para cada marca que você deseja adicionar.
8. Selecione **Aplicar**.

Depois de filtrar os dispositivos em sua lista de dispositivos, você pode executar ações neles como faria normalmente. Por exemplo, você pode selecioná-las e atribuir configurações, editar suas configurações (se estiverem Salas do Teams dispositivos) e assim por diante. Quando terminar, você poderá remover o filtro selecionando o **X** ao lado da entrada de filtro  marca ou selecionando Limpar tudo  no lado direito da lista.
