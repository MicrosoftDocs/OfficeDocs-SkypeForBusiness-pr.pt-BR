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
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 190911fcf87e0b3042bc8895ade016756a58a1ec
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23251654"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurar a rede para a Transmissão de Reunião do Skype

Depois de [Habilitar transmissão de reunião Skype](enable-skype-meeting-broadcast.md) transmissão do Skype reunião, você precisa configurar sua rede. Execute esta etapa se você deseja reter seminários na Web e outros difusões para pessoas fora da sua empresa.

Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.

Para ignorar esta etapa e, em vez disso, adicione outra empresa à sua federação, portanto, poderá convidá-los para transmissões, siga as etapas em [Permitir que os usuários entrar em contato com o Skype externo para usuários comerciais](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).

## <a name="step-1-set-up-allowed-domains"></a>Etapa 1: Configurar os domínios permitidos

Use **um** dos métodos a seguir para configurar os domínios permitidos:

###

 **Método 1: Usar o Centro de administração do Office 365**

1. Vá para o **Centro de administração do Office 365** e, em seguida, no painel de navegação esquerdo, clique em **configurações** > **serviços &amp; suplementos**e escolha **Skype para negócios**.

2. Na página **compartilhamento externo** em **exceções de domínio**, selecione **todos os domínios são bloqueados, exceto**e insira os seguintes domínios, separados-os com uma vírgula (,):

  - noammeetings.Lync.com

  - emeameetings.Lync.com

  - apacmeetings.Lync.com

  - Resources.Lync.com

3. Clique em **Salvar**.

###

 **Método 2: Usar o Windows PowerShell**

- No **Menu Iniciar**, clique com botão direito **Do Windows PowerShell** e clique em **Executar como administrador**. Na janela do **Windows PowerShell**, digite cada linha e pressione Enter.

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Etapa 2: Adicionar domínios, URLs e IP transmissão do Skype reunião endereços

A segunda etapa no processo de instalação é primeiro adicionar domínios que são necessários e, em seguida, adicionar endereços IP e URLs que são necessários para a transmissão de reunião Skype trabalhar.

- **Adicionar o Skype necessário para Business Online URLs de ponto de extremidade e endereços IP verificando quais são necessários** [aqui](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurar a Transmissão de Reunião do Skype em implantações e organizações híbridas

Se você tiver um Skype para a organização Business Online e uma implantação local do Lync Server 2010, Microsoft Lync Server 2013 e Skype para Business Server 2015 e ambos os usuários online e no local, há outras etapas de instalação que você precisará fazer em adição àquelas acima para permitir que sua organização local para se comunicar com Skype para Business Online e permitir que todos os usuários possam criar e ingressar em uma reunião do Skype transmissão. Para saber quais são esses requisitos, consulte [Configurar sua implantação local para Transmissão de Reunião do Skype](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Tópicos relacionados

[Habilitar a Transmissão de Reunião do Skype](enable-skype-meeting-broadcast.md)

[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



