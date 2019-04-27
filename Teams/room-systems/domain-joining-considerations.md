---
title: Considerações de ingresso no domínio do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.
ms.openlocfilehash: 675074cc61b60432e68317d139b20b727073961f
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362552"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Considerações de ingresso no domínio do Sistema de Salas do Skype
 
Leia este tópico para saber como ingressar o PC do cliente do Sistema de Salas do Skype em seu domínio.
  
## <a name="domain-joining-considerations"></a>Considerações de ingresso no Domínio

Você pode ingressar o aparelho de sistema de sala Skype PC no domínio do Active Directory ou deixá-lo em um grupo de trabalho. Considere os seguintes pontos antes da tomada desta decisão:
  
- O aparelho de sistema de sala Skype PC ingressando em domínio ajuda na importação de cadeia de certificados raiz privados da sua organização automaticamente.
    
- O aparelho de sistema de sala Skype PC ingressando em domínio permite conceder direitos administrativos de grupos e de usuários do domínio. Ao fazer isso, você não precisará ter que se lembrar da senha da conta do administrador no nível da máquina local.
    
- Quando você associa um aparelho de sistema de sala Skype PC ao domínio, é necessário que você crie um separado OU (unidade organizacional), para que você possa fornecer exclusões de objeto de diretiva de grupo (GPO) para a UO na qual todos os objetos de máquina de sistema de sala Skype residem. Quando você fizer isso, crie objetos de computador na unidade Organizacional antes de ingressar o aparelho de sistema de sala Skype PC no domínio.
    
- Muitas organizações têm os GPOs a seguir, que afetam as funções do sistema de sala Skype appliance PC. Certifique-se de que você deseja substituir ou bloquear a herança desses GPOs na UO Skype sala sistema: 
    
  - Tempo limite de sessões de logon (bloqueio automático)
    
  - Políticas relacionadas ao gerenciamento de energia
    
  - Requerendo etapas adicionais de autenticação
    
  - Negando acesso a unidades locais
    
  - Avisando usuários para conexões de rede lentas
    
  - Iniciar um determinado programa no logon
    
  - Crie uma outra conta de usuário de domínio em todas as máquinas que ingressaram no domínio.
    
  - Enviar o Windows Update para o sistema de sala do Skype
    
- Opcionalmente, você pode optar por deixar o PC de cliente no grupo de trabalho. Como com a área de trabalho Microsoft Teams ou Skype para o cliente de negócios, isso requer que você importar manualmente a cadeia de certificados raiz no dispositivo do sistema de sala Skype PC. Você não precisa importar a cadeia de certificados raiz, se sua implantação estiver usando um certificado público (por exemplo, Entrust, VeriSign e assim por diante). 
    
Se você planeja ingresse máquinas Skype sala sistema no domínio, para evitar a ingressar na máquina do sistema de sala Skype inadvertidamente para uma UO acidentais, que pode não estar livre de GPOs, verifique se que você ingressar a UO correta. Você pode usar o seguinte cmdlet da máquina Skype sistema de sala para ingressar na unidade Organizacional correto e não recebe GPOs que podem bloquear a funcionalidade LRS. Entre em contato com o administrador do sistema ou com o parceiro OEM para executar esses cmdlet:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Mesmo que você crie uma Unidade Organizacional e bloqueie herança, há algumas políticas que podem causar problemas a um nível superior. A configuração Política de Grupo sem Substituição supera uma UO com uma configuração Bloquear Herança de Política. Para obter mais informações, consulte o artigo [Não substituir em relação ao bloquear herança de diretiva](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) na documentação de diretiva de grupo.
  
Você pode ter várias abordagens para resolver esses problemas. Recomendamos que você consulte os especialistas em Active Directory para garantir que sejam fornecidas a você as configurações de GPO apropriadas ou pelo menos uma Unidade Organizacional na qual as políticas descritas anteriormente não existem. É recomendável para habilitar o Quality of Service (QoS) para dispositivos de sistema do Skype sala.

## <a name="see-also"></a>Confira também
  
[Configuração de Dispositivo: Criar Nova ou Editar Existente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Gerenciando a Qualidade de Serviço](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
