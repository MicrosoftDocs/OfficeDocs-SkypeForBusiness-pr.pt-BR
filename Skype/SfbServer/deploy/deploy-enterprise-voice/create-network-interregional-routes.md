---
title: Criar rotas entre regiões de rede no Skype for Business Server
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Criar ou modificar rotas entre regiões de rede, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 86b7cf9e41cb20d82f0c3c6edd6bcbd74331d553
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822491"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Criar rotas entre regiões de rede no Skype for Business Server
 
Criar ou modificar rotas entre regiões de rede, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype for Business Server. 
  
Uma rota entre regiões de rede define a rota entre um par de regiões de rede. Cada par de regiões de rede em sua implantação de controle de admissão de chamada exige uma rota entre regiões de rede. Isso permite que todas as regiões de rede da implantação acessem todas as outras regiões.
  
Enquanto os links de região definem limitações de largura de banda nas conexões entre regiões, uma rota entre regiões determina qual caminho vinculado a conexão percorrerá de uma região para outra.
  
Na topologia de exemplo, as rotas entre regiões de rede devem ser definidas para cada um dos três pares de região: América do Norte/EMEA, EMEA/APAC e América do Norte/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Para criar rotas entre regiões de rede usando o Shell de Gerenciamento do Skype for Business Server

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
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
    > A rota entre regiões de rede América do Norte/APAC requer dois links de região de rede porque não há nenhum link de região de rede direta entre eles. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Para criar rotas entre regiões de rede usando o Painel de Controle do Skype for Business Server

1. Abra o Painel de Controle do Skype for Business Server.
    
2. Na barra de navegação esquerda, clique em **Configuração de Rede**.
    
3. Clique no botão de navegações **Rota de Região**.
    
4. Clique em **Novo**.
    
5. Na página **Nova Rota de Região,** clique em **Nome** e digite um nome para a rota entre regiões de rede.
    
6. Clique em **Região de Rede 1** e clique em uma região de rede na lista que você deseja rotear para a Região de Rede 2.
    
7. Clique em **Região de Rede 2** e clique em uma região de rede na lista que você deseja rotear para a Região de Rede 1.
    
8. Clique **em Adicionar** ao lado do campo **Links** de Região de Rede e adicione um link de região de rede que será usado na rota entre regiões de rede.
    
    > [!NOTE]
    > Se você estiver criando uma rota para duas regiões de rede que não têm um link de região de rede direta de rede entre elas, deverá adicionar todos os links necessários para concluir a rota. Por exemplo, a rota entre regiões de rede América do Norte/APAC requer dois links de região de rede porque não há nenhum link de região de rede direta entre eles. 
  
9. Clique em **Confirmar**.
    
10. Para concluir a criação de rotas entre regiões de rede para sua topologia, repita as etapas 4 a 9 com as configurações de outras rotas entre regiões de rede.
    
## <a name="see-also"></a>Confira também

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
