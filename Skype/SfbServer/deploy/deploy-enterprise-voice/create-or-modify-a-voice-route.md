---
title: Criar ou modificar uma rota de voz no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: saiba como criar ou modificar uma rota de voz no Skype for Business Server usando o painel de controle do Skype for Business Server.'
ms.openlocfilehash: 8732a07e835e6888efbc132da8dc99a0b4263f29
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767794"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Criar ou modificar uma rota de voz no Skype for Business
 
**Resumo:** Saiba como criar ou modificar uma rota de voz no Skype for Business Server usando o painel de controle do Skype for Business Server.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Para criar uma rota de voz usando o painel de controle do Skype for Business Server

1. Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.
    
2. Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
4. Clique em **Rota**.
    
5. Clique em **Novo** para exibir a caixa de diálogo **Nova Rota de Voz**.
    
6. No campo **Nome**, digite o nome descritivo da rota de voz.
    
7. (Opcional) Em **Descrição**, digite outras informações descritivas para a rota de voz.
    
8. Para especificar os padrões que você deseja acomodar com essa rota, é possível usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular ou escrever manualmente a expressão regular.
    
   - Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:
    
   - **Dígitos iniciais para números que você deseja permitir**: Insira valores de prefixo que esta rota deve acomodar (incluindo o caractere + à esquerda, se necessário). Por exemplo, digite + 425 e, em seguida, clique em **Adicionar**. Repita este procedimento para cada valor de prefixo que deseja incluir na rota.
    
   - **Exceções**: se você deseja especificar uma ou mais exceções para números para um valor de prefixo, relace o prefixo e clique em **Exceções**. Digite um ou mais valores para os padrões correspondentes que você *não* deseja que essa rota acomode. Por exemplo, para excluir números que comecem com + 425237 da rota, insira um valor de + 425237 no campo **exceções** e clique em **OK**.
    
   - Para definir manualmente um padrão de correspondência, clique em **Editar** na ferramenta **Compilar um padrão para correspondências** e digite uma expressão .NET Framework regular para especificar o padrão de correspondência para números de telefone de destino aos quais a rota é aplicada. Para obter detalhes sobre como escrever expressões regulares, consulte ["expressões regulares do .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
9. Selecione **Suprimir ID de chamadas** se não quiser que o ID do telefone que está fazendo a chamada apareça no destinatário da chamada. Se você selecionar essa opção, deverá especificar uma **ID de chamada alternativa** que aparecerá na exibição da identificação de chamadas do destinatário.
    
10. Para associar um ou mais troncos à rota de voz, clique em **Adicionar** e selecione um tronco SIP ou gateway na lista.
    
11. Para associar um ou mais usos da Rede Telefônica Pública Comutada (PSTN) à rota de voz, clique em **Selecionar** e escolha um registro na lista de registros de uso do PSTN definida para sua implantação do Enterprise Voice.
    
    > [!NOTE]
    > Para exibir as propriedades de cada um dos registros de uso PSTN disponíveis, consulte [exibir registros de uso PSTN no Skype for Business](view-pstn-usage-records.md). > criar ou editar registros de uso de PSTN, consulte [criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business](voice-policy-and-pstn-usage-records.md)
  
12. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome do registro e clique na seta para cima ou para baixo.
    
    > [!NOTE]
    > Em contraste à política de voz, onde a ordem no qual os registros de uso PSTN estão listados é importante, a ordem na qual os registros de uso PSTN estão listados na rota de voz é insignificante. No entanto, recomendamos organizar a lista por frequência de uso. Por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (O Skype for Business Server percorre a lista de cima para baixo.) 
  
13. (Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.
    
14. Clique em **OK** para salvar a rota de voz.
    
    > [!IMPORTANT]
    > Sempre que você criar uma rota de voz, deverá executar o comando **Confirmar tudo** para publicar a alteração da configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>Para modificar uma rota de voz

1. Abra o painel de controle do Skype for Business Server.
    
2. Na barra de navegação à esquerda, clique em **Roteamento de Voz** e, em seguida, clique em **Rota**.
    
3. Na página **Rota**, use um dos métodos a seguir para modificar uma rota de voz:
    
   - Clique no nome de uma rota de voz, clique em **Editar** e em **Exibir detalhes**.
    
   - Clique no nome de uma rota de voz, clique em **Editar**, **Copiar** e, em seguida, em **Colar**. Clique na nova cópia da rota de voz que você acabou de criar, clique em **Editar** e em **Exibir detalhes**.
    
4. No campo **Nome** na página **Editar Rota de Voz**, digite um nome descritivo para a rota de voz.
    
5. (Opcional) No campo **Descrição**, digite informações descritivas adicionais para a rota de voz.
    
6. Para especificar os padrões a serem acomodados por esta rota, você pode usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular ou a escreva manualmente.
    
   - Para usar a ferramenta **Compilar um padrão para correspondência** para gerar uma expressão regular, digite os valores da seguinte maneira. É possível especificar dois tipos de correspondência de padrão:
    
   - **Dígitos iniciais para números que você deseja permitir**: Insira valores de prefixo que esta rota deve acomodar (incluindo o caractere + à esquerda, se necessário). Por exemplo, digite +425 e clique em **Adicionar**. Repita este procedimento para cada valor de prefixo que deseja incluir na rota.
    
   - **Exceções**: se você deseja especificar uma ou mais exceções para números para um valor de prefixo, relace o prefixo e clique em **Exceções**. Digite um ou mais valores para os padrões correspondentes que você *não* deseja que essa rota acomode. Por exemplo, para excluir números que comecem com + 425237 da rota, insira um valor de + 425237 no campo **exceções** e clique em **OK**.
    
   - Para definir o padrão de correspondência manualmente, clique em **Editar** na ferramenta **criar um padrão para corresponder** e, em seguida, digite uma expressão regular do .NET Framework para especificar o padrão correspondente para os números de telefone de destino aos quais a rota é aplicada. Para obter detalhes sobre como escrever expressões regulares, consulte ["expressões regulares do .NET Framework"](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
7. Selecione **Suprimir ID de chamadas** se não deseja que a ID do telefone que faz a chamada de saída apareça para o destinatário da chamada. Se você selecionar essa opção, deverá especificar uma **ID de chamada alternativa** que aparecerá na exibição da identificação de chamadas do destinatário.
    
8. Para associar um ou mais troncos PSTN À rota de voz, clique em **Adicionar** e selecione um tronco da lista.
    
9. Para associar um ou mais usos de PSTN à rota de voz, clique em **selecionar** e escolha um registro na lista de registros de uso PSTN definidos para a implantação do Enterprise Voice.
    
    > [!NOTE]
    > Para exibir as propriedades de cada um dos registros de uso PSTN disponíveis, consulte [exibir registros de uso PSTN no Skype for Business](view-pstn-usage-records.md). > criar ou editar registros de uso de PSTN, consulte [criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business](voice-policy-and-pstn-usage-records.md). 
  
10. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome do registro e clique na seta para cima ou para baixo.
    
    > [!NOTE]
    > Contrastando com a política de voz, em que a ordem em que os registros de uso do PSTN são listados é importante, a ordem dos registros de uso do PSTN em uma rota de voz é insignificante. No entanto, é recomendável organizar a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (O Skype for Business Server percorre a lista de cima para baixo.) 
  
11. (Opcional) Digite um valor no campo **Insira um número convertido para testar** e clique em **Ir**. Os resultados do teste são exibidos abaixo do campo.
    
12. Clique em **OK**.
    
13. Na página **Rota**, clique em **Confirmar** e em **Confirmar tudo**. 
    
    > [!NOTE]
    > Toda vez que criar ou modificar uma rota de voz, você deve executar o comando **Confirmar tudo** para publicar a alteração na configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.
  
## <a name="see-also"></a>Confira também

[Exibir registros de uso de PSTN no Skype for Business](view-pstn-usage-records.md)
  
[Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business](voice-policy-and-pstn-usage-records.md)
  
[Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md)

