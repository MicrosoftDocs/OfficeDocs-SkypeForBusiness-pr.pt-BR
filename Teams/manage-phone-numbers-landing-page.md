---
title: Gerenciar os números de telefone de sua organização
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jenstr
ms.topic: conceptual
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.overview
- ms.teamsadmincenter.voice.searchandacquire.PSTNpartner
- ms.lync.lac.NewNumberManualAcquisitionOpenSupportTicket
- ms.lync.lac.VASAMissingGeoCodes
- Calling Plans
- seo-marvel-apr2020
description: Saiba como obter e gerenciar números de telefone de usuário (assinante) e serviço (chamada tarifada e gratuita) para o Microsoft Teams para sua organização.
ms.openlocfilehash: 613a3f5f287615c6e18024d1afba1d94d0fea67c
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606740"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>Gerenciar números de telefone para sua organização

Atualmente, a Microsoft dá suporte a dois tipos de número de telefone: 

- [**Números de usuário**](#user-telephone-numbers), também chamados de números de assinante, que podem ser atribuídos aos usuários em sua organização.

- [**Números de**](#service-telephone-numbers) serviço, que são atribuídos a serviços, como [Audioconferência](deploy-audio-conferencing-teams-landing-page.md), [Atendedores Automáticos](plan-auto-attendant-call-queue.md) ou [Filas de Chamadas](plan-auto-attendant-call-queue.md).

A Microsoft está trabalhando para simplificar os tipos de número, mas, por enquanto, você precisará decidir:

- Quais locais de usuário precisam de novos números de telefone da Microsoft?
- De qual tipo de número de telefone (assinante ou serviço) preciso?
- Como fazer portar números de telefone existentes para o Teams?

A maneira como você adquire e gerencia números de telefone difere dependendo da opção de conectividade PSTN (Rede Telefônica Pública Comuada).

- Para obter informações sobre como gerenciar números de telefone para o Plano de Chamadas da Microsoft, consulte [Gerenciar números de telefone para Planos de Chamadas](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Para obter informações sobre como gerenciar números de telefone para o Operator Connect, consulte [Configurar números de telefone com o Operator Connect](operator-connect-configure.md#set-up-phone-numbers).

- Para obter informações sobre como gerenciar números de telefone para Operadora de Conexão Móvel (versão prévia pública), consulte Configurar números de telefone [com Operadora de Conexão Móvel](operator-connect-mobile-configure.md#set-up-phone-numbers).

- Para obter informações sobre como gerenciar números de telefone para Roteamento Direto, consulte [Configurar o número de telefone e habilitar a voz corporativa](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).




> [!NOTE]
> Se você precisar de tipos de número adicionais ou outros que não sejam os números vistos no Centro de administração do Microsoft Teams, poderá enviar uma solicitação de número de telefone para a Central de Serviços [de Número de Telefone](https://pstnsd.powerappsportals.com/).

## <a name="user-telephone-numbers"></a>Números de telefone do usuário

Há dois tipos de números de telefone de usuário, que podem ser atribuídos aos usuários em sua organização:  
    
- **Os números geográficos** têm uma relação com uma área geográfica e são os mais comuns. Por exemplo, números de telefone geográficos na maioria dos casos só podem ser usados em um determinado endereço, cidade, estado ou região do país.
    
- **Números não geográficos são** conhecidos como números nacionais ou, às vezes, números VoIP. Esses números não têm uma relação com uma área geográfica dentro de um país/região. Por exemplo, números não geográficos geralmente têm o mesmo custo ao chamar o número de qualquer lugar dentro do país/região. Além disso, alguns países, como a Dinamarca, têm apenas números não geográficos disponíveis.


## <a name="service-telephone-numbers"></a>Números de telefone de serviço  

Esta seção descreve os números de serviço disponíveis da Microsoft que estão incluídos em seu licenciamento. Para obter informações sobre números de serviço fornecidos pelo Operator Connect ou pelo Roteamento Direto, entre em contato com seu provedor. 

Há dois tipos de números de telefone de serviço fornecidos pela Microsoft, chamada tarifada e gratuita, que podem ser atribuídos a serviços como Audioconferência, Atendedores Automáticos ou Filas de Chamadas. Os números de serviço têm uma capacidade de chamada simultânea maior do que os números de usuário. A disponibilidade do número de serviço varia de acordo com o país/região e o tipo de número (seja um número de chamada tarifada ou gratuita). As licenças de telefonia da Microsoft em cada país/região determinam para que o número pode ser usado.
    
 - **Números de serviço de** chamada tarifada – Há dois tipos de números de serviço de chamada tarifada, que podem incorrer em um custo de chamada tarifada para o chamador:
    
   - **Números geográficos** Os números geográficos têm uma relação com uma área geográfica. Por exemplo, números de telefone geográficos na maioria dos casos só podem ser usados em um determinado endereço, cidade, estado ou região do país.
        
   - **Números não geográficos** Números não geográficos são números nacionais que não têm uma relação com uma área geográfica dentro de um país/região. Por exemplo, números não geográficos geralmente têm o mesmo custo ao chamar o número de qualquer lugar dentro do país/região.
   
- **Números de serviço de chamada** gratuita – esses números de serviço normalmente não incorrem em um custo de chamada tarifada para o chamador. O Teams fornece números nacionais de chamada gratuita em mais de 60 países/regiões.
    
    > [!CAUTION]
    > Alguns países/regiões e tipos de número de origem, como chamadas provenientes de telefones celulares, podem, em alguns casos, incorrer em um custo de chamada tarifada para o chamador. 

## <a name="where-phone-numbers-are-managed"></a>Onde os números de telefone são gerenciados

Onde e como os números são gerenciados dependem da opção de conectividade PSTN:

- Os números de telefone do Plano de Chamadas da Microsoft e do Operator Connect só podem ser gerenciados no Microsoft 365.

- Os números de telefone de Roteamento Direto podem ser gerenciados no Active Directory local ou no Microsoft 365, conforme descrito nas seções a seguir.

### <a name="direct-routing-numbers-managed-in-an-on-premises-active-directory"></a>Números de Roteamento Direto gerenciados em um Active Directory local

Se você tiver ou tiver uma implantação Skype for Business Server híbrida, o Active Directory local provavelmente está sincronizando com o Microsoft 365. Isso significa que os atributos de diretório em contas de usuário e recursos são gerenciados no Active Directory local e sincronizados no Microsoft 365.

Se o número de telefone de Roteamento Direto for gerenciado no usuário ou na conta de recurso no Active Directory local, o parâmetro msRTCSIP-Line na conta conterá um valor. Você pode usar uma ferramenta como a Edição ADSI para exibir o parâmetro msRTCSIP-Line para um usuário ou conta de recurso que tenha um número de telefone de Roteamento Direto atribuído Active Directory local.   

Depois que esse parâmetro for sincronizado automaticamente com o usuário ou a conta de recurso no Microsoft 365 por meio do processo de sincronização de diretório (Azure AD Connect), você poderá exibir o número de telefone examinando o parâmetro OnPremLineURi na saída do cmdlet [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser).

| Onde | Parâmetro | Valor |
| :------------| :-------| :---------|
| AD local | msRTCSIP-Line | tel:+14255551234 |
| Microsoft 365 | OnPremLineURi | tel:+14255551234 |

### <a name="direct-routing-numbers-managed-in-microsoft-365"></a>Números de Roteamento Direto gerenciados no Microsoft 365

Se você não estiver gerenciando números de telefone de Roteamento Direto no Active Directory local, eles serão gerenciados no Microsoft 365. Como os números de telefone não estão sincronizando com o Microsoft 365, eles não ficam visíveis no parâmetro OnPremLineUri na saída do cmdlet Get-CsOnlineUser executado para o usuário ou a conta de recurso.

### <a name="direct-routing-numbers-managed-in-both-an-on-premises-active-directory-and-microsoft-365"></a>Números de roteamento direto gerenciados em um Active Directory local e no Microsoft 365

É possível gerenciar números de telefone de Roteamento Direto de algumas contas de usuário e recursos em um Active Directory local e números de telefone de roteamento direto de outras contas no Microsoft 365. Essa funcionalidade depende se o atributo msRTCSIP-Line está definido no usuário ou na conta de recurso no Active Directory local.    

### <a name="change-where-direct-routing-phone-numbers-are-managed"></a>Alterar onde os números de telefone de Roteamento Direto são gerenciados

Para alterar onde um número de telefone de Roteamento Direto é gerenciado, você precisa remover o número de telefone do atributo msRTCSIP-Line no usuário ou resouce conta no Active Directory local.   

Para obter mais informações, [consulte Clear Skype for Business para todos os usuários locais no Active Directory](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory.md). Observe que o número de telefone precisa ser atribuído novamente ao usuário ou à conta de recurso no Microsoft 365.

Depois que a remoção tiver sido sincronizada com o Microsoft 365, o atributo OnPremLineUri na saída do Get-CsOnlineUser no usuário ou na conta de recurso estará vazio. 

