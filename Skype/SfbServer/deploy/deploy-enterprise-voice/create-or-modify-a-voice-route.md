---
title: Criar ou modificar uma rota de voz no Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Resumo: saiba como criar ou modificar uma rota de voz no Skype for Business Server usando o painel de Skype for Business Server De controle.'
ms.openlocfilehash: ee7f4a0f5d09a36fd1d8e5bcd88a15cd01cc6657
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755764"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Criar ou modificar uma rota de voz no Skype for Business
 
**Resumo:** Saiba como criar ou modificar uma rota de voz no Skype for Business Server usando o painel de Skype for Business Server Controle.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Para criar uma rota de voz usando o painel de Skype for Business Server de controle

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
4. Clique em **Rota**.
    
5. Clique em **Novo** para exibir a caixa de diálogo **Nova Rota de Voz**.
    
6. Em **Nome**, digite um nome descritivo para a rota de voz.
    
7. (Opcional) Em **Descrição,** digite informações descritivas adicionais para a rota de voz.
    
8. Para especificar os padrões que você deseja que essa rota acomode, você pode usar a ferramenta Criar um padrão para corresponder para gerar uma expressão regular ou gravar **a** expressão regular manualmente.
    
   - Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:
    
   - **Dígitos iniciais para números que você deseja permitir**: digite valores de prefixo que essa rota precisa acomodar (incluindo o + inicial, se for necessário). Por exemplo, digite +425 e clique em **Adicionar**. Repita isso para cada valor de prefixo que você deseja incluir na rota.
    
   - **Exceções**: se você quiser especificar uma ou mais exceções para números que começam com um valor de prefixo, relace o prefixo e clique em **Exceções**. Digite um ou mais valores para os padrões correspondentes que você  *não deseja*  que essa rota acomode. Por exemplo, para excluir números que começam com +425237 da rota, insira um valor de +425237 no campo **Exceções** e clique em **OK**.
    
   - Para definir manualmente o padrão de correspondência, clique em **Editar** na ferramenta **Compilar um padrão para correspondências** e digite uma expressão .NET Framework regular para especificar o padrão de correspondência para números de telefone de destino aos quais a rota é aplicada. Para obter detalhes sobre como escrever expressões regulares, consulte [".NET Framework Expressões Regulares"](/dotnet/standard/base-types/regular-expressions). 
    
9. Selecione **Suprimir ID de chamadas** se não quiser que o ID do telefone que está fazendo a chamada apareça no destinatário da chamada. Se você selecionar essa opção, deverá especificar uma **ID** do chamador alternativo que aparecerá na ID de chamada do destinatário.
    
10. Para associar um ou mais troncos à rota de voz, clique em **Adicionar** e selecione um tronco na lista.
    
11. Para associar um ou mais usos de Rede Telefônica Pública Comutado (PSTN) à rota de voz, clique em Selecionar e escolha um registro na lista de registros de uso PSTN que foram definidos para sua implantação Enterprise Voice. 
    
    > [!NOTE]
    > Para exibir as propriedades de cada um dos registros de uso PSTN disponíveis, consulte [View PSTN usage records in Skype for Business](view-pstn-usage-records.md). > Para criar ou editar registros de uso PSTN, consulte [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md)
  
12. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realça o nome do registro e clique na seta para cima ou para baixo.
    
    > [!NOTE]
    > Em contraste com uma política de voz, em que a ordem na qual os registros de uso PSTN são listados é importante, a ordem na qual os registros de uso PSTN são listados na rota de voz é insignificante. No entanto, recomendamos que você organize a lista por frequência de uso. Por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server percorre a lista de cima para baixo.) 
  
13. (Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.
    
14. Clique em **OK** para salvar a rota de voz.
    
    > [!IMPORTANT]
    > Sempre que você criar uma rota de voz, você deve executar o **comando Commit All** para publicar a alteração de configuração. Para obter detalhes, [consulte Publicar alterações pendentes na configuração de roteamento](voice-route-config-changes.md)de voz em Skype for Business . 
  
### <a name="to-modify-a-voice-route"></a>Para modificar uma rota de voz

1. Abra Skype for Business Server Painel de Controle.
    
2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e em **Rota**.
    
3. Na página **Rota**, use um dos métodos a seguir par modificar uma rota de voz:
    
   - Clique no nome de uma rota de voz, clique em **Editar** e em **Exibir detalhes**.
    
   - Clique no nome de uma rota de voz, clique em **Editar**, **Copiar** e, em seguida, em **Colar**. Clique na nova cópia da rota de voz que você acabou de criar, clique em **Editar** e em **Exibir detalhes**.
    
4. No campo **Nome** na página **Editar Rota de Voz**, digite um nome descritivo para a rota de voz.
    
5. (Opcional) No campo **Descrição**, digite informações descritivas adicionais para a rota de voz.
    
6. Para especificar os padrões que você deseja acomodar com essa rota, use a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular ou escrever manualmente a expressão regular.
    
   - Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:
    
   - **Dígitos iniciais para números que você deseja permitir**: digite valores de prefixo que essa rota precisa acomodar (incluindo o + inicial, se for necessário). Por exemplo, digite +425 e clique em **Adicionar**. Repita isso para cada valor de prefixo que você deseja incluir na rota.
    
   - **Exceções**: se você quiser especificar uma ou mais exceções para números que começam com um valor de prefixo, relace o prefixo e clique em **Exceções**. Digite um ou mais valores para os padrões correspondentes que você  *não deseja*  que essa rota acomode. Por exemplo, para excluir números que começam com +425237 da rota, insira um valor de +425237 no campo **Exceções** e clique em **OK**.
    
   - Para definir o padrão de correspondência manualmente, clique em **Editar** na ferramenta Criar um padrão para corresponder e digite uma expressão .NET Framework regular para especificar o padrão correspondente para números de telefone de destino aos quais **a** rota é aplicada. Para obter detalhes sobre como escrever expressões regulares, consulte [".NET Framework Expressões Regulares"](/dotnet/standard/base-types/regular-expressions). 
    
7. Selecione **Suprimir a ID** do chamador se você não quiser que a ID do telefone que está fazendo a chamada de saída apareça no destinatário da chamada. Se você selecionar essa opção, deverá especificar uma **ID** do chamador alternativo que aparecerá na ID de chamada do destinatário.
    
8. Para associar um ou mais troncos de rede telefônica pública comutado (PSTN) à rota de voz, clique em **Adicionar** e selecione um tronco na lista.
    
9. Para associar um ou mais usos de PSTN à rota de voz, clique em Selecionar e escolha um registro na lista de registros de uso PSTN que foram definidos para sua implantação Enterprise Voice. 
    
    > [!NOTE]
    > Para exibir as propriedades de cada um dos registros de uso PSTN disponíveis, consulte [View PSTN usage records in Skype for Business](view-pstn-usage-records.md). > Para criar ou editar registros de uso PSTN, consulte [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md). 
  
10. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realça o nome do registro e clique na seta para cima ou para baixo.
    
    > [!NOTE]
    > Em contraste com uma política de voz em que a ordem na qual os registros de uso PSTN são listados é importante, a ordem dos registros de uso PSTN em uma rota de voz é insignificante. No entanto, recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype for Business Server percorre a lista de cima para baixo.) 
  
11. (Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.
    
12. Clique em **OK**.
    
13. Na página **Rota**, clique em **Confirmar** e em **Confirmar tudo**. 
    
    > [!NOTE]
    > Sempre que você criar ou modificar uma rota de voz, você deve executar o **comando Commit all** para publicar a alteração de configuração. Para obter detalhes, [consulte Publicar alterações pendentes na](voice-route-config-changes.md) configuração de roteamento de voz Skype for Business na documentação Operações.
  
## <a name="see-also"></a>Confira também

[Exibir registros de uso de PSTN em Skype for Business](view-pstn-usage-records.md)
  
[Criar ou modificar uma política de voz e configurar registros de uso PSTN em Skype for Business](voice-policy-and-pstn-usage-records.md)
  
[Publicar alterações pendentes na configuração de roteamento de voz Skype for Business](voice-route-config-changes.md)