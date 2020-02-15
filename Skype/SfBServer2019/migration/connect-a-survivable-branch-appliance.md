---
title: Conectar um aparelho de filial persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Cada aparelho de filial persistente (SBA) é associado a um pool de front-ends que serve como um registrador de backup para o SBA. Quando o pool de front-ends é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de front-ends enquanto o pool é atualizado, após o pool ter sido migrado para o Skype for Business Server 2019, o SBA pode ser reassociado ao front E pool nd. Isso envolve excluir o SBA da topologia herdada no construtor de topologia e, em seguida, adicionar o SBA à topologia do Skype for Business Server 2019. Os usuários hospedados no SBA herdado devem ser movidos primeiro para outro pool de front-ends antes da remoção do SBA da topologia. Após a adição da SBA à topologia do Skype for Business Server 2019, esses usuários podem ser movidos de volta para o SBA. Essas etapas estão resumidas abaixo:'
ms.openlocfilehash: 7f51b9c29d6008ea3606184eb22741a489d056df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027782"
---
# <a name="connect-a-survivable-branch-appliance"></a>Conectar um aparelho de filial persistente

Cada aparelho de filial persistente (SBA) é associado a um pool de front-ends que funciona como um registrador de backup para o SBA. Quando o pool de front-ends é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de front-ends enquanto o pool é atualizado. Após o pool ter sido migrado para o Skype for Business Server 2019, o SBA pode ser novamente associado ao pool de front-ends atualizado. Isso envolve excluir o SBA da topologia herdada no construtor de topologia e, em seguida, adicionar o SBA à topologia do Skype for Business Server 2019. Os usuários hospedados no SBA herdado devem ser movidos primeiro para outro pool de front-ends antes da remoção do SBA da topologia. Depois que o SBA é adicionado à topologia do Skype for Business Server 2019, esses usuários podem ser movidos de volta para o SBA. Essas etapas estão resumidas abaixo:
  
1. Mova usuários de filial hospedados no SBA herdado para outro pool de front-ends.
    
2. Remova o SBA da topologia herdada para desconectar o pool de front-ends existente como um registrador de backup.
    
3. Adicione SBA à topologia do Skype for Business Server 2019 e configure esse novo pool de front-ends como o registrador de backup. 
    
4. Mova os usuários da filial para o novo Skype for Business Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Adicionar site de filial herdado do SBA à sua topologia

1. Abra o **Construtor de Topologia**.
    
2. No painel esquerdo, clique com o botão direito do mouse em **sites de filial**e clique em **novo site de filial**.
    
3. Na caixa de diálogo **Definir Novo Site de Filial**, clique em **Nome** e digite o nome do site de filial.
    
4. (Opcional) Clique em **Descrição** e digite uma descrição significativa para o site de filial.
    
5. Clique em **Avançar**.
    
6. (Opcional) Na próxima caixa de diálogo **Definir Novo Site de Filial**, execute uma das seguintes ações: 
    
    1. Clique em **Cidade** e digite o nome da cidade na qual o site de filial está localizado.
    
    2. Clique em **Estado/Região** e digite o nome do estado ou região na qual o site de filial está localizado.
    
    3. Clique em **Código do País** e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.
    
7. Clique em **Avançar**e, se você estiver usando um servidor ou aparelho de filial persistente neste site, não deixe de desmarcar a caixa de seleção **abrir o novo assistente persistente quando este assistente fechar** . Clique em **Concluir**.
    
8. Para associar o SBA herdado ao pool de front-ends do Skype for Business Server 2019:
    
    1. Expanda o local ramificado que foi criado. 
    
    2. Clique com o botão direito do mouse em versão legada e clique em **novo**.
    
    3. Clique em **aparelho de filial persistente**.
    
9. Siga as instruções no assistente que abrir. Para obter informações sobre itens de assistente, consulte    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Um aparelho de filial persistente só pode ser associado a um repositório de monitoramento. 
  
10. Se você não estiver usando um Aparelho de Filial Persistente ou Servidor nesse site, desmarque a caixa de seleção **Abrir o Novo Assistente Persistente quando este assistente fechar** e clique em **Concluir**.
    
11. Repita as etapas anteriores para cada site de filial que você deseja adicionar à topologia.
    

