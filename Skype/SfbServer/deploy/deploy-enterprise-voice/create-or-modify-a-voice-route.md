---
title: Criar ou modificar uma rota de voz no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Resumo: Saiba como criar ou modificar uma rota de voz no Skype for Business Server usando o Painel de Controle do Skype for Business Server.'
ms.openlocfilehash: c9f1a234bf8aeeb1bfeb05f1464a48eb0e964405
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820451"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Criar ou modificar uma rota de voz no Skype for Business
 
**Resumo:** Saiba como criar ou modificar uma rota de voz no Skype for Business Server usando o Painel de Controle do Skype for Business Server.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Para criar uma rota de voz usando o Painel de Controle do Skype for Business Server

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
4. Clique em **Rota**.
    
5. Clique em **Novo** para exibir a caixa de diálogo **Nova Rota de Voz**.
    
6. Em **Nome,** digite um nome descritivo para a rota de voz.
    
7. (Opcional) Em **Descrição,** digite informações descritivas adicionais para a rota de voz.
    
8. Para especificar os padrões que você deseja acomodar com essa rota, você pode usar a ferramenta Criar um padrão para corresponder para gerar uma expressão regular ou escrever **a** expressão regular manualmente.
    
   - Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:
    
   - **Dígitos iniciais para números que você deseja permitir**: digite valores de prefixo que essa rota precisa acomodar (incluindo o + inicial, se for necessário). Por exemplo, digite +425 e clique em **Adicionar**. Repita isso para cada valor de prefixo que você deseja incluir na rota.
    
   - **Exceções**: se você quiser especificar uma ou mais exceções para números que começam com um valor de prefixo, relace o prefixo e clique em **Exceções**. Digite um ou mais valores para os padrões de correspondência que você não  *deseja*  que essa rota acomode. Por exemplo, para excluir números começando com +425237 da rota, insira um valor  +425237 no campo Exceções e clique em **OK.**
    
   - Para definir manualmente o padrão de correspondência, clique em **Editar** na ferramenta **Compilar um padrão para correspondências** e digite uma expressão .NET Framework regular para especificar o padrão de correspondência para números de telefone de destino aos quais a rota é aplicada. Para obter detalhes sobre como escrever expressões regulares, consulte ["Expressões regulares do .NET Framework".](https://go.microsoft.com/fwlink/p/?linkId=140927) 
    
9. Selecione **Suprimir ID de chamadas** se não quiser que o ID do telefone que está fazendo a chamada apareça no destinatário da chamada. Se você selecionar essa opção, deverá especificar uma **ID** de chamada alternativa que aparecerá na exibição da ID de chamada do destinatário.
    
10. Para associar um ou mais troncos à rota de voz, clique em **Adicionar** e selecione um tronco na lista.
    
11. Para associar um ou mais usos da Rede Telefônica Pública Comutado (PSTN) à rota de voz, clique em Selecionar e escolha um registro na lista de registros de uso de PSTN que foram definidos para sua implantação do Enterprise Voice. 
    
    > [!NOTE]
    > Para exibir as propriedades de cada um dos registros de uso de PSTN disponíveis, consulte Exibir registros de uso de [PSTN no Skype for Business.](view-pstn-usage-records.md) > Para criar ou editar registros de uso de PSTN, consulte Criar ou modificar uma política de voz e configurar registros de uso de [PSTN](voice-policy-and-pstn-usage-records.md) no Skype for Business
  
12. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realça o nome do registro e clique na seta para cima ou para baixo.
    
    > [!NOTE]
    > Ao contrário de uma política de voz, em que a ordem na qual os registros de uso PSTN são listados é importante, a ordem na qual os registros de uso de PSTN são listados na rota de voz é insignificante. No entanto, recomendamos organizar a lista por frequência de uso. Por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (O Skype for Business Server percorre a lista de cima para baixo.) 
  
13. (Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.
    
14. Clique em **OK** para salvar a rota de voz.
    
    > [!IMPORTANT]
    > Sempre que criar uma rota de voz, você deve executar o comando **Commit All** para publicar a alteração na configuração. Para obter detalhes, [consulte Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business.](voice-route-config-changes.md) 
  
### <a name="to-modify-a-voice-route"></a>Para modificar uma rota de voz

1. Abra o Painel de Controle do Skype for Business Server.
    
2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e em **Rota**.
    
3. Na página **Rota**, use um dos métodos a seguir par modificar uma rota de voz:
    
   - Clique no nome de uma rota de voz, clique em **Editar** e em **Exibir detalhes**.
    
   - Clique no nome de uma rota de voz, clique em **Editar**, **Copiar** e, em seguida, em **Colar**. Clique na nova cópia da rota de voz que você acabou de criar, clique em **Editar** e em **Exibir detalhes**.
    
4. No campo **Nome** na página **Editar Rota de Voz**, digite um nome descritivo para a rota de voz.
    
5. (Opcional) No campo **Descrição**, digite informações descritivas adicionais para a rota de voz.
    
6. Para especificar os padrões que você deseja acomodar com essa rota, use a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular ou escrever manualmente a expressão regular.
    
   - Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:
    
   - **Dígitos iniciais para números que você deseja permitir**: digite valores de prefixo que essa rota precisa acomodar (incluindo o + inicial, se for necessário). Por exemplo, digite +425 e clique em **Adicionar**. Repita isso para cada valor de prefixo que você deseja incluir na rota.
    
   - **Exceções**: se você quiser especificar uma ou mais exceções para números que começam com um valor de prefixo, relace o prefixo e clique em **Exceções**. Digite um ou mais valores para os padrões de correspondência que você não  *deseja*  que essa rota acomode. Por exemplo, para excluir números começando com +425237 da rota, insira um valor  +425237 no campo Exceções e clique em **OK.**
    
   - Para definir manualmente o  padrão de correspondência, clique em Editar na ferramenta Criar um padrão para corresponder e digite uma expressão regular do .NET Framework para especificar o padrão de correspondência para números de telefone de destino aos quais **a** rota é aplicada. Para obter detalhes sobre como escrever expressões regulares, consulte ["Expressões regulares do .NET Framework".](https://go.microsoft.com/fwlink/p/?linkId=140927) 
    
7. Selecione **Suprimir ID** de chamadas se não quiser que a ID do telefone que está fazendo a chamada apareça para o destinatário da chamada. Se você selecionar essa opção, deverá especificar uma **ID** de chamada alternativa que aparecerá na exibição da ID de chamada do destinatário.
    
8. Para associar um ou mais troncos PSTN à rota de voz, clique em Adicionar e selecione um tronco na lista.
    
9. Para associar um ou mais usos de PSTN à rota de voz, clique em Selecionar e escolha um registro na lista de registros de uso de PSTN que foram definidos para sua implantação do Enterprise Voice. 
    
    > [!NOTE]
    > Para exibir as propriedades de cada um dos registros de uso de PSTN disponíveis, consulte Exibir registros de uso de [PSTN no Skype for Business.](view-pstn-usage-records.md) > Para criar ou editar registros de uso de PSTN, consulte Criar ou modificar uma política de voz e configurar registros de uso de [PSTN](voice-policy-and-pstn-usage-records.md)no Skype for Business. 
  
10. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realça o nome do registro e clique na seta para cima ou para baixo.
    
    > [!NOTE]
    > Ao contrário de uma política de voz em que a ordem na qual os registros de uso de PSTN são listados é importante, a ordem dos registros de uso de PSTN em uma rota de voz é insignificante. No entanto, recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (O Skype for Business Server percorre a lista de cima para baixo.) 
  
11. (Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.
    
12. Clique em **OK**.
    
13. Na página **Rota**, clique em **Confirmar** e em **Confirmar tudo**. 
    
    > [!NOTE]
    > Sempre que criar ou modificar uma rota de voz, você deve executar o comando **Commit all** para publicar a alteração na configuração. Para obter detalhes, [consulte Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.
  
## <a name="see-also"></a>Confira também

[Exibir registros de uso de PSTN no Skype for Business](view-pstn-usage-records.md)
  
[Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business](voice-policy-and-pstn-usage-records.md)
  
[Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md)

