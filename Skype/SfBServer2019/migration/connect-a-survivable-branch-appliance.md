---
title: Conectar um aparelho de filial persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cada aparelho de filial persistente (SBA) é associado um pool de Front-End que serve como um registrador de backup para o SBA. Quando o pool é migrado para o Skype para Business Server 2019, o SBA Front-End deve ser removido de pool Front-End, enquanto o pool é atualizado, depois que o pool foi migrado para o Skype para Business Server 2019, o SBA pode ser novamente associado a F Front atualizados pool de término. Isso envolve excluindo o SBA da topologia de legado no construtor de topologia e depois adicionar o SBA para o Skype para Business Server 2019 topologia. Usuários hospedados no SBA primeiro deve ser movido para outro pool de Front-End antes de remover o SBA da topologia de legado. Após o SBA é adicionado ao Skype para Business Server 2019 topologia, esses usuários, em seguida, podem ser movidos volta ao SBA. Essas etapas estão resumidas abaixo:'
ms.openlocfilehash: e4917b20e9e680627e92935dcb10ebf06c2e3d2d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887474"
---
# <a name="connect-a-survivable-branch-appliance"></a>Conectar um aparelho de filial persistente

Cada aparelho de filial persistente (SBA) é associado um pool de Front-End que serve como um registrador de backup para o SBA. Quando o pool de Front-End é migrado para o Skype para Business Server 2019, o SBA deve ser desassociado do pool de Front-End enquanto o pool é atualizado. Depois que o pool foi migrado para o Skype para Business Server 2019, o SBA pode ser re-associado com o pool de Front-End atualizado. Isso envolve excluindo o SBA da topologia de legado no construtor de topologia e depois adicionar o SBA para o Skype para Business Server 2019 topologia. Usuários hospedados no SBA primeiro deve ser movido para outro pool de Front-End antes de remover o SBA da topologia de legado. Depois que o SBA é adicionado ao Skype para Business Server 2019 topologia, esses usuários podem ser movidos de volta ao SBA. Essas etapas estão resumidas abaixo:
  
1. Mova os usuários ramificados hospedados no SBA herdado para outro pool de Front-End.
    
2. Remova o SBA da topologia de legado para desconectar o pool de Front-End existente como um registrador de backup.
    
3. Adicione o SBA ao Skype para Business Server 2019 topologia e configure esse novo pool de Front-End como registrador de backup. 
    
4. Mova os usuários da filial para o novo Skype para Business Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Adicionar o site de filial SBA herdado à sua topologia

1. Abra o **Construtor de topologia**.
    
2. No painel esquerdo, clique com o botão **sites de filiais**e clique em **Novo Site de filial**.
    
3. Na caixa de diálogo **Definir novo Site de filial** , clique no **nome**e, em seguida, digite o nome do site de filial.
    
4. (Opcional) Clique em **Descrição**e digite uma descrição significativa para o site de filial.
    
5. Click **Next**.
    
6. (Opcional) Na próxima caixa de diálogo **Definir novo Site de filial** , siga um destes procedimentos: 
    
    1. Clique em **Cidade**e digite o nome da cidade na qual o site de filial está localizado.
    
    2. Clique em estado/região do **** e, em seguida, digite o nome do estado ou região na qual o site de filial está localizado.
    
    3. Clique em **Código do país**e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.
    
7. Clique em **Avançar**e, em seguida, se você estiver usando um servidor ou aparelho de filial persistente neste site, não deixe de desmarque a caixa de seleção **Abrir o novo assistente persistente quando este assistente for fechado** . Clique em **Concluir**.
    
8. Para associar o SBA herdado para o Skype para pool de negócios 2019 Front-End Server:
    
    1. Expanda o site da filial que foi criado. 
    
    2. Com o botão direito na versão de legado e, em seguida, clique em **novo**.
    
    3. Clique em **aparelho de filial persistente**.
    
9. Siga as instruções no assistente que é aberta. Para obter informações sobre os itens do assistente, consulte    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Um aparelho de filial persistente só pode ser associado um repositório de monitoramento. 
  
10. Se você não estiver usando um servidor ou aparelho de filial persistente neste site, desmarque a caixa de seleção **Abrir o novo assistente persistente quando este assistente for fechado** e clique em **Concluir**.
    
11. Repita as etapas anteriores para cada site de filial que você deseja adicionar à topologia.
    

