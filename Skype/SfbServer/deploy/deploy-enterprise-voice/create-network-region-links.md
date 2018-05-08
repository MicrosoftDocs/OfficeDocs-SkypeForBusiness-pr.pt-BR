---
title: Criar links de região de rede no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Criar ou modificar os links de região de rede, que são usados pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server.
ms.openlocfilehash: e0fbabb811ec604b3a0155074a01bc4b02bd6152
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="create-network-region-links-in-skype-for-business-server-2015"></a>Criar links de região de rede no Skype for Business Server 2015
 
Criar ou modificar os links de região de rede, que são usados pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server. 
  
Regiões dentro de uma rede são vinculadas através de uma conectividade WAN física. Um link de região de rede cria um link entre duas regiões configuradas para o controle de admissão de chamadas (CAC) e define as limitações de largura de banda de tráfego de áudio e vídeo entre essas regiões.
  
A topologia de exemplo possui um link entre as regiões da América do Norte e APAC e um link entre as regiões EMEA e APAC. Cada um desses links de região é restrito por largura de banda WAN, conforme descrito na tabela de informações de largura de banda do Link de região no [exemplo: coletando os requisitos para o controle de admissão de chamada no Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Para criar links de região de rede usando Skype do Shell de gerenciamento do servidor de negócios

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o cmdlet New-CsNetworkRegionLink para criar os links de região e aplicar os perfis da política de largura de banda adequados. Por exemplo, execute:
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Para criar links de região de rede usando o Skype para o painel de controle do servidor de negócios

1. Abra o Skype para painel de controle do servidor de negócios.
    
2. Na barra de navegação esquerda, clique em **Configuração de rede**.
    
3. Clique no botão de navegação **Link de região**.
    
4. Clique em **Novo**.
    
5. Na página **Novo link de região**, clique em **Nome** e digite um nome para o link de região de rede.
    
6. Clique em **Região de rede 1** e clique na região de rede da lista que deseja vincular para a Região de rede 2.
    
7. Clique em **Região de rede 2** e clique na região de rede da lista que deseja vincular para a Região de rede 1.
    
8. Opcionalmente, clique em **Política da largura de banda** e selecione o perfil da política de largura de banda que deseja aplicar para o link de região de rede.
    
    > [!NOTE]
    > Aplique uma política de largura de banda apenas se o link de região de rede é restrito por largura de banda e se deseja usar o CAC para controlar o tráfego de mídia naquele link. 
  
9. Clique em **Confirmar**.
    
10. Para finalizar a criação de links de região de rede para sua topologia, repita as etapas 4 a 9 com as configurações de outras regiões.
    
## <a name="see-also"></a>Consulte também

#### 

[New-CsNetworkRegionLink.](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink.](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)

