---
title: Criar rede rotas interregional no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Criar ou modificar rotas interregional da rede, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server.
ms.openlocfilehash: b099910a6881958919ed9707424a9ae77f0f8983
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978915"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Criar rede rotas interregional no Skype para Business Server
 
Criar ou modificar rotas interregional da rede, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server. 
  
Uma rota entre regiões de rede define a rota entre um par de regiões de rede. Cada par de regiões de rede em sua implantação do serviço de controle de admissão de chamadas exige uma rota entre regiões de rede. Isso permite que cada região da rede dentro da implantação acesse todas as demais regiões.
  
Enquanto os vínculos de região definem limitações de largura de banda nas conexões entre regiões, uma rota entre regiões de rede determina o caminho vinculado que a conexão percorrerá de uma região à outra.
  
Na topologia de exemplo, as rotas entre regiões de rede devem ser definidas para cada um dos três pares de regiões: América do Norte/EMEA, EMEA/APAC e América do Norte/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Para criar rotas interregional de rede usando Skype do Shell de gerenciamento do servidor de negócios

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o cmdlet **New-CsNetworkInterRegionRoute** para definir as rotas necessárias. Por exemplo, execute:
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > A rota entre regiões de rede América do Norte/APAC requer dois links de regiões de rede porque não há um link de região de rede direta entre elas. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Para criar rotas interregional de rede usando o Skype para o painel de controle do servidor de negócios

1. Abra o Skype para painel de controle do servidor de negócios.
    
2. Na barra de navegação esquerda, clique em **Configuração de rede**.
    
3. Clique no botão de navegações **Rota de Região**.
    
4. Clique em **Novo**.
    
5. Na página **Nova Rota de Região**, clique em **Nome** e digite um nome para a rota entre regiões de rede.
    
6. Clique em **Região de Rede 1** e clique em uma região de rede na lista que você deseja rotear para a Região de Rede 2.
    
7. Clique em **Região de Rede 2** e clique em uma região de rede na lista que você deseja rotear para a Região de Rede 1.
    
8. Clique em **Adicionar** próximo ao campo **Links de Região de Rede** e adicione um link de região de rede que será usado na rota entre regiões de rede.
    
    > [!NOTE]
    > Se você estiver criando uma rota para duas regiões de rede que não têm um link de região de rede direta de rede entre elas, deverá adicionar todos os links necessários para concluir a rota. Por exemplo, a rota entre regiões de rede América do Norte/APAC requer dois links de região de rede porque não há nenhum link de região de rede direta entre elas. 
  
9. Clique em **Confirmar**.
    
10. Para concluir a criação de rotas entre regiões de rede para sua topologia de rede, repita as etapas 4 a 9 com configurações de outras rotas entre regiões de rede.
    
## <a name="see-also"></a>Consulte também

[New-CsNetworkInterRegionRoute.](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute.](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute.](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute.](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)