---
title: Conectar um aparelho de filial persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cada aplicativo de ramificação sobreviventes (SBA) está associado a um pool de front-end que serve como registrador de backup para o SBA. Quando o pool de front-ends é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de front-ends enquanto o pool é atualizado, assim que o pool é migrado para o Skype for Business Server 2019, o SBA pode ser reassociado ao E frontal atualizado nd pool. Isso envolve excluir o SBA da topologia herdada no construtor de topologias e, em seguida, adicionar o SBA à topologia do Skype for Business Server 2019. Os usuários hospedados no SBA herdado devem primeiro ser movidos para outro pool de front-end antes de remover SBA da topologia. Depois que o SBA é adicionado à topologia do Skype for Business Server 2019, esses usuários podem ser movidos de volta para o SBA. Estas etapas estão resumidas abaixo:'
ms.openlocfilehash: 7cb933018d24dafb978464338f01f97b25e15539
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275542"
---
# <a name="connect-a-survivable-branch-appliance"></a>Conectar um aparelho de filial persistente

Cada aplicativo de ramificação sobreviventes (SBA) está associado a um pool de front-end que funciona como registrador de backup para o SBA. Quando o pool de front-ends é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de front-ends enquanto o pool é atualizado. Após a migração do pool para o Skype for Business Server 2019, o SBA pode ser associado novamente ao pool de front-end atualizado. Isso envolve excluir o SBA da topologia herdada no construtor de topologias e, em seguida, adicionar o SBA à topologia do Skype for Business Server 2019. Os usuários hospedados no SBA herdado devem primeiro ser movidos para outro pool de front-end antes de remover SBA da topologia. Após a SBA ser adicionada à topologia do Skype for Business Server 2019, esses usuários podem ser removidas para o SBA. Estas etapas estão resumidas abaixo:
  
1. Mova os usuários da ramificação na SBA herdada para outro pool de front-ends.
    
2. Remova o SBA da topologia herdada para desconectar o pool de front-end existente como um registrador de backup.
    
3. Adicione SBA à topologia do Skype for Business Server 2019 e configure esse novo pool de front-end como o registrador de backup. 
    
4. Mova os usuários da filial para o novo Skype for Business Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Adicionar site de ramificação SBA herdada à sua topologia

1. Abrir o **Construtor**de topologias.
    
2. No painel esquerdo, clique com o botão direito do mouse em **sites**de ramificação e clique em **novo site de filial**.
    
3. Na caixa de diálogo **definir novo site de filial** , clique em **nome**e digite o nome do site de filial.
    
4. Adicionais Clique em **Descrição**e digite uma descrição significativa para o site da filial.
    
5. Click **Next**.
    
6. Adicionais Na caixa de diálogo próximo **definir novo site** de filiais, siga um destes procedimentos: 
    
    1. Clique em **cidade**e digite o nome da cidade na qual o site da filial está localizado.
    
    2. Clique em **estado/região**e, em seguida, digite o nome do Estado ou da região em que o site da filial está localizado.
    
    3. Clique em **código do país**e, em seguida, digite o código de chamada de dois dígitos para o país/região no qual o site da filial está localizado.
    
7. Clique em **Avançar**e, se você estiver usando um aplicativo ou aplicativo de ramificação sobreviventes neste site, certifique-se de desmarcar a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** . Clique em **Concluir**.
    
8. Para associar o SBA herdado ao pool de front-ends do Skype for Business Server 2019:
    
    1. Expanda o site de ramificação que foi criado. 
    
    2. Clique com o botão direito do mouse em versão herdada e clique em **novo**.
    
    3. Clique em **aparelho para ramificação sobreviventes**.
    
9. Siga as instruções no assistente que é aberto. Para obter informações sobre itens do assistente, consulte    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Um aparelho de ramificação sobreviventes só pode ser associado a uma loja de monitoramento. 
  
10. Se você não estiver usando um aplicativo ou aplicativo de ramificação sobreviventes neste site, desmarque a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** e clique em **concluir**.
    
11. Repita as etapas anteriores para cada site de ramificação que você deseja adicionar à topologia.
    

