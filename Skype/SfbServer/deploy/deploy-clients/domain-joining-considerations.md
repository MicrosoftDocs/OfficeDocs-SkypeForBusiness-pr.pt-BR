---
title: Considerações sobre como ingressar no domínio do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Leia este tópico para saber como ingressar um PC do dispositivo do Sistema de Sala do Skype em seu domínio.
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805911"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Considerações sobre como ingressar no domínio do Sistema de Sala do Skype
 
Leia este tópico para saber como ingressar um PC do dispositivo do Sistema de Sala do Skype em seu domínio.
  
## <a name="domain-joining-considerations"></a>Considerações de associação de domínio

Você pode ingressar o PC do dispositivo do Sistema de Sala do Skype no domínio do Active Directory ou deixá-lo em um Grupo de Trabalho. Considere os seguintes pontos antes de tomar essa decisão:
  
- Ingressar no domínio do PC do dispositivo do Sistema de Sala do Skype ajuda a importar automaticamente a cadeia de certificado raiz privada da sua organização.
    
- Ingressar no domínio do PC do dispositivo do Sistema de Sala do Skype permite conceder direitos administrativos a usuários e grupos de domínio. Ao fazer isso, você não terá que se lembrar da senha da conta de administrador no nível do computador local.
    
- Ao ingressar um PC de dispositivo do Sistema de Salas do Skype no domínio, é necessário criar uma Unidade Organizacional (UO) separada para que você possa fornecer exclusões de Objeto de Política de Grupo (GPO) para a UO onde residem todos os objetos da máquina do Sistema de Salas do Skype. Ao fazer isso, crie objetos de máquina na UO antes de ingressar o PC do dispositivo do Sistema de Sala do Skype no domínio.
    
- Muitas organizações têm os seguintes GPOs, que afetam as funções do PC do dispositivo do Sistema de Sala do Skype. Substitua ou bloqueie a herança desses GPOs na UO do Sistema de Sala do Skype: 
    
  - Tempo final das sessões de logon (bloqueio automático)
    
  - Políticas relacionadas ao gerenciamento de energia
    
  - Exigir etapas adicionais de autenticação
    
  - Negando o acesso a unidades locais
    
  - Solicitando aos usuários conexões de rede lentas
    
  - Iniciar um determinado programa no logon
    
  - Crie outra conta de usuário de domínio em todos os máquinas ingressas no domínio.
    
  - Push Windows Update to Skype Room System
    
- Como alternativa, você pode optar por deixar o PC do dispositivo no grupo de trabalho. Assim como no cliente do Skype for Business para área de trabalho, isso exige que você importe manualmente a cadeia de certificado raiz no PC do dispositivo do Sistema de Sala do Skype. Você não será obrigado a importar a cadeia de certificado raiz se a implantação do Skype for Business estiver usando um certificado público (por exemplo, Suspensão, VeriSign e assim por diante). 
    
Se você planeja ingressar máquinas do Sistema de Sala do Skype no domínio, para evitar ingressar inadvertidamente na máquina do Sistema de Sala do Skype em uma UO não intencional, que pode não estar livre de GPOs, certifique-se de ingressar na UO correta. Você pode usar o seguinte cmdlet da máquina do Sistema de Sala do Skype para ingressar na UO correta e não recebe GPOs que podem bloquear a funcionalidade do LRS. Entre em contato com o administrador do sistema ou com o parceiro OEM para executar estes cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Mesmo que você crie uma UO separada e bloqueie a herança, há algumas políticas que podem causar problemas em um nível superior. Uma configuração política de grupo sem substituição supera uma UO com uma configuração bloquear herança de política. Para obter mais informações, consulte o artigo [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação da Política de Grupo.
  
Você pode ter várias abordagens para resolver esses problemas. Aconselhamos você a consultar seus especialistas do Active Directory para garantir que você tenha uma UO que tenha as configurações de GPO apropriadas ou pelo menos uma UO na qual as políticas descritas anteriormente não existam. É aconselhável habilitar a QoS (Qualidade de Serviço) para dispositivos do Sistema de Sala do Skype.

## <a name="see-also"></a>Confira também
  
[Configuração de Dispositivo: Criar Nova ou Editar Existente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gerenciando a Qualidade de Serviço](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
