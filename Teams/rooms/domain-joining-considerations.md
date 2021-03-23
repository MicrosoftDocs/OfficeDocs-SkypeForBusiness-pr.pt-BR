---
title: Considerações de ingresso no domínio do Sistema de Salas do Skype
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: O administrador pode aprender sobre como ingressar um computador de dispositivo do Sistema de Sala do Skype a um domínio do Active Directory, juntamente com as considerações para fazer isso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 806dcac8f73f555227c03f7612f30fe4a598812f
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997409"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Considerações de ingresso no domínio do Sistema de Salas do Skype
 
Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.
  
## <a name="domain-joining-considerations"></a>Considerações de ingresso no Domínio

Você pode ingressar o computador de dispositivo do Sistema de Sala do Skype no domínio do Active Directory ou deixá-lo em um Grupo de Trabalho. Considere os seguintes pontos antes da tomada desta decisão:
  
- A junção de domínio ao computador de dispositivo do Sistema de Sala do Skype ajuda a importar automaticamente a cadeia de certificados raiz privada da sua organização.
- A junção de domínio ao computador de dispositivo do Sistema de Sala do Skype permite que você conceda direitos administrativos a usuários e grupos de domínio. Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.
- Ao ingressar em um computador de dispositivo do Sistema de Sala do Skype no domínio, é necessário criar uma Unidade Organizacional (OU) separada, para que você possa fornecer exclusões de OBJETO de Política de Grupo (GPO) para a UO onde todos os objetos de máquina do Sistema de Sala do Skype residem. Ao fazer isso, crie objetos de máquina na UO antes de ingressar no computador de dispositivo do Sistema de Sala do Skype no domínio.
- Muitas organizações têm os seguintes GPOs, que afetam as funções de computador do dispositivo do Sistema de Sala do Skype. Verifique se você substitui ou bloqueia a herança desses GPOs na UO do Sistema de Sala do Skype:

  - Tempo limite de sessões de logon (bloqueio automático)
  - Políticas relacionadas ao gerenciamento de energia
  - Requerendo etapas adicionais de autenticação
  - Negando acesso a unidades locais
  - Avisando usuários para conexões de rede lentas
  - Iniciar um determinado programa no logon
  - Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.
  - Push Windows Update to Skype Room System
    
- Opcionalmente, você pode optar por deixar o PC de cliente no grupo de trabalho. Assim como no microsoft teams da área de trabalho ou cliente do Skype for Business, isso exige que você importe manualmente a cadeia de certificados raiz no computador de dispositivo do Sistema de Sala do Skype. Não é necessário importar a cadeia de certificados raiz se sua implantação estiver usando um certificado público (por exemplo, Entrust, VeriSign e assim por diante). 
    
Se você planeja ingressar máquinas do Sistema de Sala do Skype no domínio, para evitar ingressar a máquina do Sistema de Sala do Skype inadvertidamente em uma UO não intencional, que pode não estar livre de GPOs, certifique-se de ingressar na OU correta. Você pode usar o seguinte cmdlet da máquina do Sistema de Sala do Skype para ingressar na OU correta e não recebe GPOs que podem bloquear a funcionalidade LRS. Entre em contato com o administrador do sistema ou com o parceiro OEM para executar esses cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Mesmo que você crie uma UO separada e bloqueie a herança, existem algumas políticas que podem causar problemas em um nível superior. A configuração Política de Grupo sem Substituição supera uma UO com uma configuração Bloquear Herança de Política. Para obter mais informações, consulte [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação da Política de Grupo.
  
Você pode ter várias abordagens para resolver esses problemas. Recomendamos que você consulte seus especialistas do Active Directory para garantir que você tenha uma OU que tenha configurações de GPO apropriadas ou pelo menos uma UO na qual as políticas descritas anteriormente não existem. Recomendamos a habilitação de QoS (Qualidade de Serviço) para dispositivos do Sistema de Sala do Skype.

## <a name="related-topics"></a>Tópicos relacionados
  
[Configuração de Dispositivo: Criar Nova ou Editar Existente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gerenciando a Qualidade de Serviço](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)
