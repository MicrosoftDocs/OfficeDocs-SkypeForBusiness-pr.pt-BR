---
title: Configurar a rede para a Transmissão de Reunião do Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: f9a85a1f64f88b55d99c7a27694a46b7ea885849
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301284"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurar a rede para a Transmissão de Reunião do Skype

Depois de habilitar a transmissão de [reunião do Skype](enable-skype-meeting-broadcast.md) para a transmissão de reunião do Skype, você precisa configurar sua rede. Siga este procedimento se quiser manter o webinars e outras difusões para pessoas de fora da sua empresa.

Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.

Para ignorar esta etapa e adicionar outra empresa à sua Federação para poder convidá-las para difusões, siga as etapas em [permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).

## <a name="step-1-set-up-allowed-domains"></a>Etapa 1: configurar domínios permitidos

Use **um** dos seguintes métodos para configurar os domínios permitidos:

## #

 **Método 1: usar o centro de administração do Office 365**

1. Vá para o **centro de administração do Office 365** e, em seguida, na barra de navegação à esquerda, clique em **configurações** > de**Serviços &amp; **e em suplementos e escolha **Skype for Business**.

2. Na página **compartilhamento externo** em **exceções de domínio**, selecione **todos os domínios estão bloqueados, exceto**e insira os seguintes domínios, separados por uma vírgula (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Clique em **Salvar**.

## #

 **Método 2: usar o Windows PowerShell**

- No **menu iniciar**, clique com o botão direito do mouse em **Windows PowerShell** e clique em **Executar como administrador**. Na janela do **Windows PowerShell**, digite cada linha e pressione Enter.

  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Etapa 2: adicionar domínios de transmissão de reunião do Skype, URLs e endereços IP

A segunda etapa no processo de instalação é para você primeiro adicionar domínios que são necessários e adicionar endereços IP e URLs necessários para que a transmissão de reunião do Skype funcione.

- **Adicione as URLs e os endereços IP do ponto de extremidade do Skype for Business online necessários vendo quais são necessários** [aqui](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurar a Transmissão de Reunião do Skype em implantações e organizações híbridas

Se você tiver uma organização do Skype for Business Online e uma implantação local do Lync Server 2010, do Microsoft Lync Server 2013 e do Skype for Business Server 2015 e tiver usuários online e local, há outras etapas de configuração que serão necessárias adição aos itens acima para permitir que sua organização local se comunique com o Skype for Business Online e permita que todos os usuários ingressem em uma transmissão de reunião do Skype. Para saber quais são esses requisitos, consulte [Configurar sua implantação local para Transmissão de Reunião do Skype](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Tópicos relacionados

[Habilitar a Transmissão de Reunião do Skype](enable-skype-meeting-broadcast.md)

[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



