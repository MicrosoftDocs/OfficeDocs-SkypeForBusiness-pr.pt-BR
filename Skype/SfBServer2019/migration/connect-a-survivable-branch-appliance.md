---
title: Conectar um aparelho de filial persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Cada Dispositivo de FilialVivível (SBA) está associado a um pool de Front-End que serve como um registrador de backup para o SBA. Quando o pool de Front-End é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de Front-End enquanto o pool é atualizado, Depois que o pool for migrado para o Skype for Business Server 2019, o SBA poderá ser reassociado com o pool de Front-End atualizado. Isso envolve excluir o SBA da topologia herdda no Construtor de Topologias e adicionar o SBA à topologia Skype for Business Server 2019. Os usuários que estão no SBA herdado devem primeiro ser movidos para outro pool de Front-End antes de remover o SBA da topologia. Depois que o SBA for adicionado à topologia Skype for Business Server 2019, esses usuários poderão ser movidos de volta para o SBA. Essas etapas estão resumidas abaixo:'
ms.openlocfilehash: 4977868c45b274adea514d84e251f682da02cc8ee486a5a182d984ee652f3ae2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313869"
---
# <a name="connect-a-survivable-branch-appliance"></a>Conectar um aparelho de filial persistente

Cada Dispositivo de FilialVivível (SBA) está associado a um pool de Front-End que serve como um registrador de backup para o SBA. Quando o pool de Front-End é migrado para o Skype for Business Server 2019, o SBA deve ser desassociado do pool de Front-End enquanto o pool é atualizado. Depois que o pool for migrado para o Skype for Business Server 2019, o SBA poderá ser reassociado ao pool de Front-End atualizado. Isso envolve excluir o SBA da topologia herdda no Construtor de Topologias e adicionar o SBA à topologia Skype for Business Server 2019. Os usuários que estão no SBA herdado devem primeiro ser movidos para outro pool de Front-End antes de remover o SBA da topologia. Depois que o SBA for adicionado à topologia Skype for Business Server 2019, esses usuários poderão ser movidos de volta para o SBA. Essas etapas estão resumidas abaixo:
  
1. Mover usuários de filial que estão no SBA herdado para outro pool de Front-End.
    
2. Remova o SBA da topologia herdado para desconectar o pool de Front-End existente como registrador de backup.
    
3. Adicione o SBA à topologia Skype for Business Server 2019 e configure esse novo pool de Front-End como registrador de backup. 
    
4. Mova os usuários de filial para o novo Skype for Business Server SBA 2019.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Adicionar site de filial SBA herddo à sua topologia

1. Abra o **Construtor de Topologia**.
    
2. No painel esquerdo, clique com o botão direito do mouse em **Sites de Filial** e clique em **Novo Site de Filial.**
    
3. Na caixa de diálogo **Definir Novo Site de Filial**, clique em **Nome** e digite o nome do site de filial.
    
4. (Opcional) Clique em **Descrição** e digite uma descrição significativa para o site de filial.
    
5. Clique em **Avançar**.
    
6. (Opcional) Na próxima caixa de diálogo **Definir Novo Site de Filial**, execute uma das seguintes ações: 
    
    1. Clique em **Cidade** e digite o nome da cidade na qual o site de filial está localizado.
    
    2. Clique em **Estado/Região** e digite o nome do estado ou região na qual o site de filial está localizado.
    
    3. Clique em **Código do País** e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.
    
7. Clique **em** Próximo e, em seguida, se você estiver usando um Aparelho de Filial Ou Servidor Desavivável neste site, certifique-se de limpar a caixa de seleção **Abrir** o Novo Assistente De Sobrevivência quando esse assistente fechar. Clique em **Concluir**.
    
8. Para associar o SBA herdados ao pool de front-end Skype for Business Server 2019:
    
    1. Expanda o local ramificado que foi criado. 
    
    2. Clique com o botão direito do mouse na versão herdada e clique em **Novo**.
    
    3. Clique **em Aparelho de Filial Suportável.**
    
9. Siga as instruções no assistente que abrir. Para obter informações sobre itens do assistente, consulte    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Um Aparelho de Filial Desavivável só pode ser associado a um Armazenamento de Monitoramento. 
  
10. Se você não estiver usando um Aparelho de Filial Persistente ou Servidor nesse site, desmarque a caixa de seleção **Abrir o Novo Assistente Persistente quando este assistente fechar** e clique em **Concluir**.
    
11. Repita as etapas anteriores para cada site de filial que você deseja adicionar à topologia.
