---
title: Configurar contas para salas de equipes da Microsoft
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: Leia este tópico para saber mais sobre como configurar contas para salas de equipes da Microsoft no Exchange e Skype para negócios.
ms.openlocfilehash: 7606f31dde96236111b4a44919427245fa32215d
ms.sourcegitcommit: 856793c99fc02fb016383d0b6f8411c386d78886
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/12/2019
ms.locfileid: "31828948"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar contas para salas de equipes da Microsoft
 
Leia este tópico para saber mais sobre as salas de equipes da Microsoft e como ele se integra com o Exchange e Skype para negócios.
  
Este tópico apresenta como criar as contas usadas por salas de equipes da Microsoft em Microsoft Exchange e Skype para negócios. Instruções de implantação para os dispositivos de salas de equipes da Microsoft é abordada em [Configure um console de salas de equipes da Microsoft](console.md). É provável que sua infraestrutura esteja incluída em uma destas configurações:
  
- Implantação online: ambiente da sua organização estiver implantado inteiramente no Office 365. Para obter mais informações, consulte [Implantar o Microsoft equipes salas com o Office 365](with-office-365.md).
    
- Implantação no local: sua organização tem servidores que ele controla, onde o Active Directory, Exchange e Skype para Business Server são hospedados. Para obter mais informações, consulte [Implantar o Microsoft equipes salas com Skype para Business Server](with-skype-for-business-server-2015.md)
    
- Implantações híbridas: sua organização tem uma mistura de serviços, com algumas hospedados no local e algumas hospedadas online por meio do Office 365. Com salas de equipes da Microsoft, os seguintes cenários híbridos são suportados: 
    
  - Exchange Online com Skype para Business Server no local. Para obter mais informações, consulte [Implantar o Microsoft equipes salas com o Exchange Online (híbrido)](with-exchange-online.md).
    
  - Para negócios Online do Exchange no local com Skype. Para obter mais informações, consulte [Implantar o Microsoft equipes salas com o Exchange no local (híbrido)](with-exchange-on-premises.md).
    
A configuração do dispositivo depende da configuração que você tem.
  
Salas de equipes da Microsoft precisa ser atribuído a uma conta"dispositivo" no Active Directory, Exchange e Skype para negócios. A conta é usada para acessar seu calendário de reunião e estabelecer Skype para conectividade de negócios. As pessoas podem reservar essa conta agendando uma reunião com ela. Salas de equipes da Microsoft poderão ingressar essa reunião e forneça vários recursos para os participantes da reunião.
  
> [!IMPORTANT]
> Sem uma conta de dispositivo, nenhum desses recursos funcionará. 
  
Cada conta de dispositivo é exclusiva para um único dispositivo de salas de equipes da Microsoft e requer algumas instalação:
  
- A conta do dispositivo deve ser configurada corretamente.
    
- Sua infra-estrutura deve ser configurada para permitir a salas de equipes da Microsoft para validar a conta do dispositivo e acessar os serviços Microsoft apropriados.
    
> [!IMPORTANT]
> É recomendável que a conta seja criada antes da instalação do hardware. O ideal é iniciar a preparação da conta de duas a três semanas antes da instalação. Em ambientes híbridos, a conta usada para salas de equipes da Microsoft deve ter habilitada no Sync AAD porque a autenticação de salas de equipes da Microsoft requer autenticação de 365 0ffice de sincronização de senha.
  
Você pode considerar uma conta do dispositivo como a conta do recurso que pessoas reconhecem como conta de uma conferência da sala ou uma reunião do espaço. Para agendar uma reunião usando essa sala de conferência, convide a conta para essa reunião. Para usar o Microsoft equipes salas mais eficiência, faça o mesmo com a conta de dispositivo que é atribuída a cada uma delas.
  
Se você já tiver uma conta de caixa de correio de recurso definido para esse espaço de reunião onde você está instalando salas de equipes da Microsoft, você pode alterar essa conta de recurso analisadas um dispositivo. Depois disso, tudo o que você precisa fazer é adicionar a conta de dispositivo a um dispositivo de salas de equipes da Microsoft. Veja exemplos de configuração de conta de dispositivo fornecidos abaixo.
  
Com uma configuração adicional, gerenciamento remoto é possível usando o Microsoft Azure Monitor conforme descrito em [gerenciamento de planejar salas de equipes da Microsoft com o Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [gerenciamento de implantar o Microsoft equipes salas com o Azure Monitor](azure-monitor.md)e [ Gerenciar salas de equipes da Microsoft dispositivos com o Windows Azure Monitor](../../manage/skype-room-systems-v2/azure-monitor.md). 
  
## <a name="basic-configuration"></a>Configuração básica

Essas propriedades representam a configuração mínima para uma conta de dispositivo funcionar com o Microsoft equipes salas. Sua conta de dispositivo pode exigir o programa de instalação.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Caixa de correio do Exchange (Exchange 2013 SP1 ou posterior, ou Exchange Online)  <br/> |Habilitando a conta com uma caixa de correio do Exchange concede à conta de dispositivo a capacidade de receber e enviar email e solicitações de reunião e para exibir um calendário de reuniões no dispositivo Microsoft equipes salas. A caixa de correio de salas de equipes da Microsoft deve ser uma caixa de correio de sala.  <br/> |
|Skype para a empresa está habilitado  <br/> |Skype para negócios deve ser habilitado para usar vários recursos de conferência, como chamadas de vídeo, mensagens Instantâneas e compartilhamento de tela. Skype para Business Online e o Skype para Business Server são suportados.  <br/> |
|Habilitado por senha  <br/> |A conta do dispositivo deve ser ativada com uma senha ou ele não pode autenticar com o Exchange ou Skype para Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuração avançada

Enquanto as propriedades para a configuração básica permitirá que a conta do dispositivo a ser configurado em um ambiente simple, é possível que seu ambiente tem outras restrições em contas de diretório que devem ser atendidas na ordem para salas de equipes da Microsoft usar com êxito o conta do dispositivo.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Autenticação baseada em certificado  <br/> |Certificados podem ser necessários para o Exchange e Skype para Business Server. Para implantar certificados, você pode carregá-los quando estiver conectado como Administrador.  <br/> |
   
A maneira mais fácil de configurar as contas do dispositivo é configurá-los usando o Windows PowerShell remoto. A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de dispositivo ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de dispositivo compatíveis salas de equipes da Microsoft.
  
Se você preferir usar a interface do usuário do Office 365 sobre cmdlets do Windows PowerShell, algumas etapas podem ser realizadas manualmente. Consulte o [tópico Criando uma conta de dispositivo usando o Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).
  
## <a name="see-also"></a>Consulte Também

[Planejar para salas de equipes da Microsoft](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Configurar um console de salas de equipes da Microsoft](console.md)
  
[Gerenciar salas de equipes da Microsoft](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

