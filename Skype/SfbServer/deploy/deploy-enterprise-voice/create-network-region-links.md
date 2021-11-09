---
title: Criar links de região de rede em Skype for Business Server
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Crie ou modifique links de região de rede, que são usados Enterprise Voice controle de admissão de chamada em Skype for Business Server.
ms.openlocfilehash: 0d6d3fd1c3f432135352477051cab157e5979d33
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860888"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Criar links de região de rede em Skype for Business Server
 
Crie ou modifique links de região de rede, que são usados Enterprise Voice controle de admissão de chamada em Skype for Business Server. 
  
As regiões dentro de uma rede são vinculadas por meio da conectividade Wan. Um link de região de rede cria um link entre duas regiões configuradas para o Controle de Admissão de Chamada (CAC) e define as limitações de largura de banda no tráfego de áudio e vídeo entre essas regiões.
  
A topologia de exemplo possui um link entre as regiões da América do Norte e APAC e um link entre as regiões EMEA e APAC. Cada um desses links de região é restrito pela largura de banda WAN, conforme descrito na tabela Informações de Largura de Banda de Link de Região em [Exemplo:](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)reunir requisitos para controle de admissão de chamada em Skype for Business Server .
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Para criar links de região de rede usando Skype for Business Server Shell de Gerenciamento

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
2. Execute o cmdlet New-CsNetworkRegionLink para criar os links de região e aplicar os perfis da política de largura de banda adequados. Por exemplo, execute:
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Para criar links de região de rede usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.
    
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
    
## <a name="see-also"></a>Confira também

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)