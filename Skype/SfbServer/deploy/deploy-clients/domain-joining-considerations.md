---
title: Skype Considerações sobre a junção de domínio do Sistema de Sala
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Leia este tópico para saber como ingressar um computador Skype de dispositivo do Sistema de Sala ao seu domínio.
ms.openlocfilehash: d3c94a4983bddb051bda29badf5c569eeef635a3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844864"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype Considerações sobre a junção de domínio do Sistema de Sala
 
Leia este tópico para saber como ingressar um computador Skype de dispositivo do Sistema de Sala ao seu domínio.
  
## <a name="domain-joining-considerations"></a>Considerações de associação de domínio

Você pode ingressar o computador Skype de dispositivo do Sistema de Sala ao domínio do Active Directory ou deixá-lo em um Grupo de Trabalho. Considere os seguintes pontos antes de tomar essa decisão:
  
- A junção de domínio ao computador do Skype do sistema de sala ajuda a importar automaticamente a cadeia de certificados raiz privada da sua organização.
    
- A junção de domínio ao computador Skype do sistema de sala permite conceder direitos administrativos a usuários e grupos de domínio. Ao fazer isso, não será preciso lembrar a senha da conta de administrador de nível de máquina local.
    
- Quando você instala um computador de dispositivo do sistema de sala do Skype no domínio, é necessário criar uma UO (Unidade Organizacional) separada, para que você possa fornecer exclusões de OBJETO de Política de Grupo (GPO) para a UO onde residem todos os objetos de máquina do sistema de sala do Skype. Ao fazer isso, crie objetos de máquina na UO antes de ingressar no computador de dispositivo do sistema de sala Skype no domínio.
    
- Muitas organizações têm os seguintes GPOs, que afetam Skype funções de computador de dispositivo do Sistema de Sala. Verifique se você substitui ou bloqueia a herança desses GPOs na UO do sistema de sala Skype sala: 
    
  - Tempo de tempo de sessões de logon (bloqueio automático)
    
  - Políticas relacionadas ao gerenciamento de energia
    
  - Exigindo etapas adicionais de autenticação
    
  - Negando o acesso a unidades locais
    
  - Solicitando aos usuários conexões de rede lentas
    
  - Iniciar um determinado programa no logon
    
  - Crie outra conta de usuário de domínio em todos os máquinas ingressas no domínio.
    
  - Push Windows Update to Skype Room System
    
- Como alternativa, você pode optar por deixar o computador do dispositivo no grupo de trabalho. Assim como no cliente de Skype for Business desktop, isso exige que você importe manualmente a cadeia de certificados raiz no computador do Skype do sistema de sala. Você não é obrigado a importar a cadeia de certificados raiz se sua implantação Skype for Business estiver usando um certificado público (por exemplo, Confiando, VeriSign e assim por diante). 
    
Se você planeja ingressar Skype máquinas do Sistema de Sala ao domínio, para evitar ingressar o computador do sistema de sala do Skype inadvertidamente em uma UO não intencional, que pode não estar livre de GPOs, certifique-se de ingressar na UO correta. Você pode usar o cmdlet a seguir do computador do sistema de sala Skype para ingressar na OU correta e não recebe GPOs que podem bloquear a funcionalidade LRS. Entre em contato com o administrador do sistema ou com o parceiro OEM para executar estes cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Mesmo que você crie uma UO separada e bloqueie a herança, existem algumas políticas que podem causar problemas em um nível mais alto. Uma configuração de Política de Grupo sem Substituição supera uma UO com uma configuração de Herança de Política de Bloqueio. Para obter mais informações, consulte o artigo [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação da Política de Grupo.
  
Você pode ter várias abordagens para resolver esses problemas. Recomendamos que você consulte seus especialistas do Active Directory para garantir que você tenha uma OU que tenha configurações de GPO apropriadas ou pelo menos uma UO na qual as políticas descritas anteriormente não existem. É aconselhável habilitar a QoS (Qualidade do Serviço) para dispositivos Skype Room System.

## <a name="see-also"></a>Confira também
  
[Configuração de Dispositivo: Criar Nova ou Editar Existente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gerenciando a qualidade do serviço](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)