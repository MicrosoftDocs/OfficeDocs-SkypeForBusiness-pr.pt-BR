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
f1.keywords:
- CSH
description: Saiba como gerenciar e filtrar marcas em seus dispositivos Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d29bc28de39c8d145914d3bddab4ed949ad0a338
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962892"
---
# <a name="manage-microsoft-teams-device-tags"></a>Gerenciar marcas de dispositivo do Microsoft Teams

As marcas de dispositivo no Microsoft Teams permitem que você agrupe, organize e gerencie com mais facilidade os dispositivos que você implantou em sua organização. Com o centro de administração do Microsoft Teams, você pode adicionar uma ou mais marcas em dispositivos, usar filtros para exibir dispositivos que correspondam à marca especificada e, em seguida, executar ações para os dispositivos que têm essa marca.

Você pode adicionar uma marca de dispositivo a mais de um tipo de dispositivo. No entanto, quando você abre um painel de dispositivos no centro de administração, somente os dispositivos desse tipo são retornados. Por exemplo, você pode atribuir a marca "corporativa" a dispositivos de salas de equipe e telefones. Se você procurar a marca "corporativa" enquanto estiver em **dispositivos**  >  **Phones**, somente telefones serão retornados. Da mesma forma, se você procurar pela marca "Corporate" em salas de equipe de **dispositivos**  >  **Teams Rooms**, apenas dispositivos de salas de equipe serão retornados.

Para gerenciar marcas de dispositivo, você precisa ser um administrador global, administrador de serviços do teams ou administrador de dispositivo do teams. Para obter mais informações sobre funções de administrador, consulte [usar funções de administrador do Microsoft Teams para gerenciar o Teams](../using-admin-roles.md).

> [!IMPORTANT]
> As marcas de dispositivo são atribuídas à conta de recurso que está conectada a um dispositivo. Se você assinar uma conta de recurso de um dispositivo e usá-la para se conectar a outros dispositivos, as marcas de dispositivo serão aplicadas a um novo dispositivo.

## <a name="create-remove-or-rename-device-tags"></a>Criar, remover ou renomear marcas de dispositivo

Usando o painel de gerenciamento de marcas de dispositivo, você pode:

- Veja todas as marcas do seu dispositivo.
- Crie várias marcas de dispositivo facilmente e atribua-as a dispositivos mais tarde. As marcas podem ter até 25 caracteres.
- Remova marcas de dispositivo que não são mais necessárias. Antes de remover uma marca de dispositivo, você precisa removê-la de todos os dispositivos aos quais ela foi adicionada.
- Renomear marcas de dispositivo. Quando você renomeia uma marca de dispositivo, essa alteração é refletida em todos os dispositivos aos quais ela foi adicionada. As marcas podem ter até 25 caracteres.

1. Acesse o centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Navegue até os **dispositivos** e escolha qualquer painel de dispositivos, como **telefones**.
3. Selecione **ações** no canto superior direito da página e selecione **todas as marcas de dispositivo**.
4. Para criar uma marca de dispositivo, selecione **+ Adicionar**, forneça um valor para a marca do dispositivo e selecione o ícone **salvar** .
5. Para remover uma marca de dispositivo, selecione as reticências **...** ao lado da marca de dispositivo que você deseja remover e selecione **excluir**.
    > [!NOTE]
    > Se você tentar remover uma marca de dispositivo adicionada aos dispositivos, receberá uma mensagem perguntando se deseja removê-la de todos os dispositivos. Se você quiser fazer isso e continuar a remover a marca do dispositivo, selecione Remover **dispositivos**.
6. Para renomear uma marca de dispositivo, selecione as reticências **...** ao lado da marca de dispositivo que você deseja renomear e selecione **Editar**. Forneça um novo valor para a marca do dispositivo e selecione o ícone **salvar** .

## <a name="add-or-remove-tags-on-a-single-device"></a>Adicionar ou remover marcas em um único dispositivo

Ao adicionar marcas a um dispositivo, você pode selecionar uma marca existente ou criar uma nova. As marcas podem ter até 25 caracteres.

1. Acesse o centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Navegue até os **dispositivos** e escolha o painel do dispositivo que contém o dispositivo ao qual você deseja adicionar ou remover marcas.
3. Coloque uma marca de seleção ao lado do dispositivo ao qual você deseja adicionar ou remover marcas e selecione **gerenciar marcas**.
4. Se você quiser adicionar uma marca:
    1. Comece a digitar o nome da marca que você deseja adicionar.
    2. Se a marca já existir, selecione-a na lista de marcas que são retornadas.
    3. Se a marca não existir, selecione **Adicionar " \<tag name> " como uma nova marca**. As marcas podem ter até 25 caracteres.
5. Se você quiser remover uma marca, selecione **X** ao lado da marca que deseja remover.
6. Repita as etapas acima se desejar adicionar ou remover mais marcas.
7. Selecione **aplicar**.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Adicionar ou remover marcas em vários dispositivos

Ao adicionar marcas a um dispositivo, você pode selecionar uma marca existente ou criar uma nova. As marcas podem ter até 25 caracteres. Se quiser remover uma marca de vários dispositivos, você precisará selecionar o usuário do teams que está associado ao dispositivo e remover a marca do usuário.

1. Acesse o centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Navegue até os **dispositivos** e escolha o painel do dispositivo que contém os dispositivos nos quais você deseja adicionar ou remover marcas.
3. Coloque uma marca de seleção ao lado dos dispositivos que você deseja adicionar ou remover marcas e selecione **gerenciar marcas**.
4. Se você quiser adicionar uma marca:
    1. Comece a digitar o nome da marca que você deseja adicionar em **gerenciar marcas para todos os dispositivos de usuários do teams**.
    2. Se a marca já existir, selecione-a na lista de marcas que são retornadas.
    3. Se a marca não existir, selecione **Adicionar " \<tag name> " como uma nova marca**.
5. Se você quiser remover uma marca:
    1. Expanda **Selecionar usuários do teams**.
    2. Expanda as ** \<x> marcas** sob o nome do usuário do teams do qual você deseja remover as marcas.
    3. Selecione **X** ao lado da marca que você deseja remover.
6. Repita as etapas acima se desejar adicionar ou remover mais marcas.
7. Selecione **aplicar**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Usar filtros para retornar dispositivos com uma marca específica

Se você tiver adicionado marcas de dispositivo aos seus dispositivos, poderá usá-las para filtrar a lista de dispositivos para retornar somente os dispositivos que tiveram uma marca específica adicionada a elas. Isso pode ser útil se você só quiser ver todos os dispositivos em uma sala específica, todos os dispositivos de um determinado tipo ou outros critérios usados ao adicionar suas marcas. Você também pode executar ações em massa em dispositivos retornados, como a aplicação de atualizações em ondas ou a configuração de políticas de configuração diferentes dependendo dos grupos de dispositivos identificados usando marcas de dispositivo.

1. Acesse o centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Navegue até os **dispositivos** e escolha o painel do dispositivo que contém os dispositivos que você deseja filtrar.
3. Selecione o ícone de **filtro** .
4. Se você só quiser especificar uma única marca ou se quiser localizar dispositivos com todas as marcas especificadas, selecione **corresponder a todas essas condições**.
5. Se você quiser localizar dispositivos que correspondam a uma ou mais marcas de dispositivo, selecione **correspondam a qualquer uma dessas condições**.
6. Selecione o campo de **marca** e, em seguida, especifique um nome de marca de dispositivo no campo **Inserir um valor** .
7. Se você quiser adicionar mais marcas de dispositivo, selecione **adicionar mais** e repita a etapa 6 para cada marca que você deseja adicionar.
8. Selecione **aplicar**.

Depois de filtrar os dispositivos na lista de dispositivos, você pode executar ações neles normalmente. Por exemplo, você pode selecionar as configurações e, em seguida, atribuir configurações, editar suas configurações (se elas forem dispositivos de salas de equipe) e assim por diante. Quando terminar, você pode remover o filtro selecionando o **X**  ao lado da entrada do filtro de **marca** ou selecionando **limpar tudo** no lado direito da lista.
