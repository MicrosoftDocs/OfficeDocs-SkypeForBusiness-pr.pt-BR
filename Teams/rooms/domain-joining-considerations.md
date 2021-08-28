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
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: O administrador pode aprender sobre como ingressar um computador do Skype de dispositivos do Sistema de Sala a um domínio do Active Directory, juntamente com as considerações para fazer isso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7956160f57971e48f1f979a7c0a905d760b767bd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579595"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Considerações de ingresso no domínio do Sistema de Salas do Skype
 
Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.
  
## <a name="domain-joining-considerations"></a>Considerações de ingresso no Domínio

Você pode ingressar o computador Skype de dispositivo do Sistema de Sala ao domínio do Active Directory ou deixá-lo em um Grupo de Trabalho. Considere os seguintes pontos antes da tomada desta decisão:
  
- A junção de domínio ao computador do Skype do sistema de sala ajuda a importar automaticamente a cadeia de certificados raiz privada da sua organização.
- A junção de domínio ao computador Skype de dispositivo do Sistema de Sala permite conceder direitos administrativos a usuários de domínio e grupos. Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.
- Quando você instala um computador de dispositivo do sistema de sala do Skype no domínio, é necessário criar uma UO (Unidade Organizacional) separada, para que você possa fornecer exclusões de Objeto de Política de Grupo (GPO) para a UO onde residem todos os objetos de máquina do Sistema de Salas do Skype. Ao fazer isso, crie objetos de máquina na UO antes de ingressar no computador de dispositivo do sistema de sala Skype ao domínio.
- Muitas organizações têm os seguintes GPOs, que afetam Skype funções de computador de dispositivo do Sistema de Sala. Certifique-se de substituir ou bloquear a herança desses GPOs na UO do sistema de sala Skype sala:

  - Tempo limite de sessões de logon (bloqueio automático)
  - Políticas relacionadas ao gerenciamento de energia
  - Requerendo etapas adicionais de autenticação
  - Negando acesso a unidades locais
  - Avisando usuários para conexões de rede lentas
  - Iniciar um determinado programa no logon
  - Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.
  - Push Windows Update to Skype Room System
    
- Opcionalmente, você pode optar por deixar o PC de cliente no grupo de trabalho. Assim como com o cliente Microsoft Teams ou Skype for Business desktop, isso exige que você importe manualmente a cadeia de certificados raiz no computador do dispositivo Skype Room System. Não é necessário importar a cadeia de certificados raiz se sua implantação estiver usando um certificado público (por exemplo, Entrust, VeriSign e assim por diante). 
    
Se você planeja ingressar Skype máquinas do Sistema de Sala ao domínio, para evitar ingressar o computador do sistema de sala do Skype inadvertidamente em uma UO não intencional, que pode não estar livre de GPOs, certifique-se de ingressar na UO correta. Você pode usar o cmdlet a seguir da máquina do sistema de sala Skype para ingressar na OU correta e não recebe GPOs que podem bloquear a funcionalidade LRS. Entre em contato com o administrador do sistema ou com o parceiro OEM para executar esses cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Mesmo que você crie uma UO separada e bloqueie a herança, existem algumas políticas que podem causar problemas em um nível superior. A configuração Política de Grupo sem Substituição supera uma UO com uma configuração Bloquear Herança de Política. Para obter mais informações, consulte [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação da Política de Grupo.
  
Você pode ter várias abordagens para resolver esses problemas. Recomendamos que você consulte seus especialistas do Active Directory para garantir que você tenha uma OU que tenha configurações de GPO apropriadas ou pelo menos uma UO na qual as políticas descritas anteriormente não existem. Recomendamos a habilitação de QoS (Qualidade de Serviço) para dispositivos Skype Room System.

## <a name="related-topics"></a>Tópicos relacionados
  
[Configuração de Dispositivo: Criar Nova ou Editar Existente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gerenciando a Qualidade de Serviço](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)