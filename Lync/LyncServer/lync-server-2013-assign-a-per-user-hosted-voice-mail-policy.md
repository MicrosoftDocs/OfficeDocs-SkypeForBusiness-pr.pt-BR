---
title: 'Lync Server 2013: atribuir uma política de correio de voz hospedada por usuário'
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
ms.openlocfilehash: 95413733a9b23ce1f749ebb16521a3349b00165d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722951"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Atribuir uma política de correio de voz hospedada por usuário no Lync Server 2013

 


A implantação de uma ou mais políticas de correio de voz hospedadas por usuário é opcional. Se você implantar políticas por usuário, deverá atribuí-las explicitamente a usuários, grupos ou objetos de contato.

Para obter detalhes sobre como atribuir ou remover a atribuição de políticas de correio de voz hospedadas por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - Grant CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>Para atribuir uma política de correio de voz hospedada por usuário

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet Grant-CsHostedVoicemailPolicy para atribuir a política de caixa postal hospedada por usuário a usuários individuais, grupos e objetos de contato. Por exemplo, execute:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    Este exemplo atribuiu a política de caixa postal hospedada pela webmail ao usuário Ken Myer.
    
    **Identidade** especifica a conta de usuário a ser modificada. O valor IDENTITY pode ser especificado usando qualquer um dos seguintes formatos:
    
      - O endereço SIP do usuário
    
      - O nome de usuário do Active Directory do usuário do Active Directory
    
      - O nome de logon\\do domínio do usuário (por exemplo\\, contoso kenmyer)
    
      - O nome de exibição dos serviços de domínio Active Directory do usuário (por exemplo, Ken Myer). Se estiver usando o nome de exibição como o valor de identidade, você poderá usar o\*caractere curinga asterisco (). Por exemplo, a identidade "\* Smith" retorna todos os usuários que têm um nome de exibição que termina com o valor de cadeia de caracteres "Smith".
    

    > [!NOTE]  
    > O nome de conta SAM do Active Directory do usuário não pode ser usado como o valor de identidade porque o SAM-Account-Name não é necessariamente exclusivo na floresta.


