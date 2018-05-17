---
title: Configurar contas para sistemas de sala Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ''
description: Leia este tópico para saber mais sobre como configurar contas para sistemas de sala Skype v2 no Exchange e Skype para Business Server 2015.
ms.openlocfilehash: 0514d1b542e8fa53f7210992d5cb219f7e9a7719
ms.sourcegitcommit: 265fbdc1a8ac566751e707874656bd6b90de980d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2018
---
# <a name="configure-accounts-for-skype-room-systems-v2"></a>Configurar contas para sistemas de sala Skype v2
 
Leia este tópico para saber mais sobre os sistemas de sala Skype v2 e como ele se integra com o Exchange e Skype para Business Server 2015.
  
Este tópico apresenta como criar as contas usadas por sistemas de sala Skype v2 no Microsoft Exchange e Skype para Business Server 2015. Instruções de implantação para dispositivos do Skype sala sistemas v2 é abordada em [Configure um console do Skype sala sistemas v2](console.md). É provável que sua infraestrutura esteja incluída em uma destas configurações:
  
- Implantação online: ambiente da sua organização estiver implantado inteiramente no Office 365. Para obter mais informações, consulte [implantar sistemas de sala Skype v2 com o Office 365](with-office-365.md).
    
- Implantação no local: sua organização tem servidores que ele controla, onde o Active Directory, Exchange e Skype para Business Server 2015 são hospedados. Para obter mais informações, consulte [implantar sistemas de sala Skype v2 com Skype para Business Server 2015](with-skype-for-business-server-2015.md)
    
- Implantação híbrida: sua organização tem uma mistura de serviços, com algumas hospedados no local e algumas hospedadas online por meio do Office 365. Com sistemas de sala Skype v2, há suporte para os seguintes cenários híbridos: 
    
  - Exchange Online com Skype para negócios 2015 de servidor no local. Para obter mais informações, consulte [implantar sistemas de sala Skype v2 com o Exchange Online (híbrido)](with-exchange-online.md).
    
  - Para negócios Online do Exchange no local com Skype. Para obter mais informações, consulte [implantar sistemas de sala Skype v2 com o Exchange no local (híbrido)](with-exchange-on-premises.md).
    
A configuração do dispositivo depende da configuração que você tem.
  
Sistemas de sala Skype v2 precisa ser atribuído a uma conta de usuário"" no Active Directory, Exchange e Skype para negócios. A conta é usada para acessar seu calendário de reunião e estabelecer Skype para conectividade de negócios. As pessoas podem reservar essa conta agendando uma reunião com ela. Sistemas de sala Skype v2 poderão ingressar essa reunião e forneça vários recursos para os participantes da reunião.
  
> [!IMPORTANT]
> Sem uma conta de usuário, nenhum desses recursos funcionará. 
  
Cada conta de usuário é exclusiva para um único dispositivo v2 Skype sistemas de sala e requer algumas instalação:
  
- A conta de usuário deve ser configurada corretamente.
    
- Sua infra-estrutura deve ser configurada para permitir que os sistemas de sala Skype v2 para validar a conta de usuário e acessar os serviços Microsoft apropriados.
    
> [!IMPORTANT]
> É recomendável que a conta seja criada antes da instalação do hardware. O ideal é iniciar a preparação da conta de duas a três semanas antes da instalação. 
  
Você pode considerar uma conta de usuário como a conta do recurso que pessoas reconhecem como conta de uma conferência da sala ou uma reunião do espaço. Para agendar uma reunião usando essa sala de conferência, convide a conta para essa reunião. Para usar sistemas de sala Skype v2 mais eficiência, faça o mesmo com a conta de usuário que é atribuída a cada uma delas.
  
Se você já tiver uma conta de caixa de correio de recurso definido para esse espaço de reunião onde você está instalando sistemas de sala Skype v2, você pode alterar essa conta de recurso em uma conta de usuário. Depois disso, tudo o que você precisa fazer é adicionar a conta de usuário a um dispositivo de v2 de sistemas de sala Skype. Veja os exemplos de configuração de conta de usuário fornecidos a seguir.
  
Com uma configuração adicional, gerenciamento remoto é possível usando o pacote de gerenciamento de operações da Microsoft (OMS) conforme descrito em [sistemas de sala Skype planejar gerenciamento de v2 com OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [gerenciamento de v2 implantar sistemas do Skype sala com OMS](with-oms.md)e [Gerenciar Dispositivos de v2 de sistemas de sala Skype com OMS](../../manage/skype-room-systems-v2/oms.md). 
  
## <a name="basic-configuration"></a>Configuração básica

Essas propriedades representam a configuração mínima para uma conta de usuário funcionar com sistemas de sala Skype v2. Sua conta de usuário pode exigir configurações adicionais.
  
|**Propriedade**|**Finalidade**|
|:-----|:-----|
|Caixa de correio do Exchange (Exchange 2013 SP1 ou posterior, ou Exchange Online)  <br/> |Habilitando a conta com uma caixa de correio do Exchange oferece a conta de usuário a capacidade de receber e enviar email e solicitações de reunião e para exibir um calendário de reuniões no dispositivo v2 Skype sistemas de sala. A caixa de correio do Skype sala sistemas v2 deve ser uma caixa de correio de sala.  <br/> |
|Skype para a empresa está habilitado  <br/> |Skype para negócios deve ser habilitado para usar vários recursos de conferência, como chamadas de vídeo, mensagens Instantâneas e compartilhamento de tela. Skype para Business Online e o Skype para Business Server são suportados.  <br/> |
|Habilitado por senha  <br/> |A conta de usuário deve ser ativada com uma senha ou ele não pode autenticar com o Exchange ou Skype para Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuração avançada

Enquanto as propriedades para a configuração básica permitirá que a conta de usuário seja configurado em um ambiente simple, é possível que seu ambiente tem outras restrições em contas de diretório que devem ser atendidas para que os sistemas de sala Skype v2 usar com êxito o conta de usuário.
  
|**Propriedade**|**Finalidade**|
|:-----|:-----|
|Autenticação baseada em certificado  <br/> |Certificados podem ser necessários para o Exchange e Skype para Business Server. Para implantar certificados, você pode carregá-los quando estiver conectado como Administrador.  <br/> |
   
A melhor maneira de configurar as contas de usuário é configurá-los usando o Windows PowerShell remoto. A Microsoft fornece [SkypeRoomProvisioningScript.ps1](room-systems-v2-scripts.md), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de v2 Skype sala sistemas compatíveis.
  
Se você preferir usar a interface do usuário do Office 365 sobre cmdlets do Windows PowerShell, algumas etapas podem ser realizadas manualmente. Consulte o [tópico Criando uma conta de dispositivo usando o Office 365](https://technet.microsoft.com/itpro/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Consulte também

#### 

[Planejar a sala Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Configurar um console v2 de sistemas de sala do Skype](console.md)
  
[Gerenciar Skype sala v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

