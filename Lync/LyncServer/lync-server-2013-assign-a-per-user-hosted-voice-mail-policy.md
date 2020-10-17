---
title: 'Lync Server 2013: atribuir uma política de caixa postal hospedada por usuário'
description: 'Lync Server 2013: atribua uma política de caixa postal hospedada por usuário.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559887"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Atribuir uma política de caixa postal hospedada por usuário no Lync Server 2013

 


A implantação de uma ou mais políticas de caixa postal hospedada por usuário é opcional. Se você implantar políticas por usuário, deverá atribui-las explicitamente a usuários, grupos ou objetos de contato.

Para obter detalhes sobre como atribuir ou remover a atribuição de políticas de caixa postal hospedadas por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>Para atribuir uma política de caixa postal hospedada por usuário

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet Grant-CsHostedVoicemailPolicy para atribuir a política de caixa postal hospedada por usuário a usuários individuais, grupos e objetos de contato. Por exemplo, execute:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    Esse exemplo atribuiu a política de caixa postal hospedada ExRedmond ao usuário Ken Myer.
    
    **Identidade** especifica a conta de usuário a ser modificada. O valor de Identidade pode ser especificado usando qualquer um dos seguintes formatos:
    
      - O endereço SIP do usuário
    
      - O nome UPN do Active Directory do usuário
    
      - O nome de logon do domínio do usuário \\ (por exemplo, Contoso \\ kenmyer)
    
      - O Nome de exibição de serviços de domínio do Active Directory do usuário (por exemplo, Ken Myer). Se estiver usando o Display-Name como o valor de identidade, você poderá usar o \* caractere curinga asterisco (). Por exemplo, a identidade " \* Smith" retorna todos os usuários que têm um Display-Name que termina com o valor de cadeia de caracteres "Smith".
    

    > [!NOTE]  
    > O Nome de conta SAM do Active Directory do usuário não pode ser usado como o valor de Identidade, pois o Nome de conta SAM não é necessariamente exclusivo na floresta.


