---
title: Criar rotas interregionais de rede em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Crie ou modifique rotas interregionais de rede, que são usadas Enterprise Voice controle de admissão de chamada em Skype for Business Server.
ms.openlocfilehash: 4aa831c33049e2e77a298f96de80d9bad2d296e4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833867"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Criar rotas interregionais de rede em Skype for Business Server
 
Crie ou modifique rotas interregionais de rede, que são usadas Enterprise Voice controle de admissão de chamada em Skype for Business Server. 
  
Uma rota interregional de rede define a rota entre um par de regiões de rede. Cada par de regiões de rede em sua implantação de controle de admissão de chamada requer uma rota interregional de rede. Isso permite que todas as regiões de rede da implantação acessem todas as outras regiões.
  
Enquanto os links de região definem limitações de largura de banda nas conexões entre regiões, uma rota interregional determina qual caminho vinculado a conexão percorrerá de uma região para outra.
  
Na topologia de exemplo, as rotas interregionais de rede devem ser definidas para cada um dos três pares de região: América do Norte/EMEA, EMEA/APAC e América do Norte/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Para criar rotas interregionais de rede usando Skype for Business Server Shell de Gerenciamento

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
2. Execute o cmdlet **New-CsNetworkInterRegionRoute** para definir as rotas necessárias. Por exemplo, execute:
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > A rota interregional de rede da América do Norte/APAC requer dois links de região de rede porque não há um link de região de rede direta entre eles. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Para criar rotas interregionais de rede usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.
    
2. Na barra de navegação esquerda, clique em **Configuração de Rede**.
    
3. Clique no botão de navegações **Rota de Região**.
    
4. Clique em **Novo**.
    
5. Na página **Nova Rota de Região,** clique em **Nome** e digite um nome para a rota interregional de rede.
    
6. Clique em **Região de Rede 1** e clique em uma região de rede na lista que você deseja rotear para a Região de Rede 2.
    
7. Clique em **Região de Rede 2** e clique em uma região de rede na lista que você deseja rotear para a Região de Rede 1.
    
8. Clique **em Adicionar** ao lado do campo Links de **Região** de Rede e adicione um link de região de rede que será usado na rota interregional de rede.
    
    > [!NOTE]
    > Se você estiver criando uma rota para duas regiões de rede que não têm um link de região de rede direta de rede entre elas, deverá adicionar todos os links necessários para concluir a rota. Por exemplo, a rota interregional de rede américa do norte/APAC requer dois links de região de rede porque não há link de região de rede direta entre eles. 
  
9. Clique em **Confirmar**.
    
10. Para concluir a criação de rotas interregionais de rede para sua topologia, repita as etapas de 4 a 9 com configurações para outras rotas interregionais de rede.
    
## <a name="see-also"></a>Confira também

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)