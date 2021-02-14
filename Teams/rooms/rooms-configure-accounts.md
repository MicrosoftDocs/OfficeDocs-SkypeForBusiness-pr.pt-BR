---
title: Configurar contas para salas do Microsoft Teams
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
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: Leia este tópico para saber mais sobre como configurar contas para Salas do Microsoft Teams no Exchange e no Skype for Business.
ms.openlocfilehash: e171ef22dd1733c06b03a4a9483f591d73d70cb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662516"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>Configurar contas para salas do Microsoft Teams
 
Leia este tópico para saber mais sobre as Salas do Microsoft Teams e como ele se integra ao Exchange e ao Skype for Business.
  
Este tópico apresenta como criar contas usadas pelas Salas do Microsoft Teams no Microsoft Exchange e no Skype for Business. As instruções de implantação para dispositivos de Salas do Microsoft Teams estão cobertas [em Configurar um console de Salas do Microsoft Teams.](console.md) É provável que sua infraestrutura esteja incluída em uma destas configurações:
  
- Implantação online: o ambiente da sua organização é totalmente implantado no Microsoft 365 ou no Office 365. Para obter mais informações, [consulte Implantar Salas do Microsoft Teams com o Microsoft 365 ou o Office 365.](with-office-365.md)
    
- Implantação local: sua organização tem servidores que ela controla, onde o Active Directory, o Exchange e o Skype for Business Server estão hospedados. Para obter mais informações, [consulte Implantar Salas do Microsoft Teams com o Skype for Business Server](with-skype-for-business-server-2015.md)
    
- Implantações híbridas: sua organização tem uma combinação de serviços, com alguns hospedados no local e alguns hospedados online por meio do Microsoft 365 ou do Office 365. Com o Microsoft Teams Rooms, há suporte para os seguintes cenários híbridos:
    
  - Exchange Online com o Skype for Business Server local. Para obter mais informações, [consulte Implantar Salas do Microsoft Teams com o Exchange Online (híbrido).](with-exchange-online.md)
    
  - Exchange local com o Microsoft Teams ou o Skype for Business Online. Para obter mais informações, [consulte Implantar Salas do Microsoft Teams com o Exchange local (híbrido).](with-exchange-on-premises.md)
    
A configuração do dispositivo depende da configuração que você tem.
  
As Salas do Microsoft Teams precisam ter uma "conta de dispositivo" no Active Directory, no Exchange e no Skype for Business. A conta é usada para acessar o calendário da reunião e estabelecer a conectividade do Microsoft Teams ou do Skype for Business. As pessoas podem reservar essa conta agendando uma reunião com ela. As Salas do Microsoft Teams poderão ingressar na reunião e fornecer vários recursos aos participantes da reunião.
  
> [!IMPORTANT]
> Sem uma conta de dispositivo, nenhum desses recursos funcionará. 
  
Cada conta de dispositivo é exclusiva de um único dispositivo do Microsoft Teams Rooms e requer alguma configuração:
  
- A conta do dispositivo deve estar configurada corretamente.
    
- Sua infraestrutura deve ser configurada para permitir que as Salas do Microsoft Teams validem a conta do dispositivo e alcancem os serviços apropriados da Microsoft.
    
> [!IMPORTANT]
> É recomendável que a conta seja criada antes da instalação do hardware. O ideal é iniciar a preparação da conta de duas a três semanas antes da instalação. 

Em ambientes híbridos, a conta usada para Salas do Microsoft Teams deve ter a sincronização de senha habilitada na sincronização do Azure Active Directory (AAD), pois a autenticação de Salas do Microsoft Teams requer autenticação do Microsoft 365 ou do Office 365. Ao configurar a conta, certifique-se de que o endereço SIP da conta corresponde ao nome upn (nome de usuário principal) no AAD. 
  
Você pode pensar em uma conta de dispositivo como a conta de recurso que as pessoas reconhecem como uma conta de sala de conferência ou espaço de reunião. Para agendar uma reunião usando essa sala de conferência, convide a conta para essa reunião. Para usar as Salas do Microsoft Teams com mais eficiência, faça o mesmo com a conta do dispositivo atribuída a cada uma delas.
  
Se você já tiver uma conta de caixa de correio de recurso configurada para o espaço de reunião onde você está instalando salas do Microsoft Teams, poderá transformar essa conta de recurso em uma conta de dispositivo. Depois de fazer isso, basta adicionar a conta do dispositivo a um dispositivo do Microsoft Teams Rooms. Veja os exemplos de configuração de conta de dispositivo fornecidos abaixo.
  
Com configurações adicionais, o gerenciamento remoto é possível usando o Monitor do Microsoft Azure conforme descrito no Plano de Gerenciamento de Salas do Microsoft Teams com o [Monitor do Azure,](azure-monitor-plan.md)implantar o gerenciamento de salas do Microsoft Teams com o [Monitor do Azure](azure-monitor-deploy.md)e gerenciar dispositivos de salas do Microsoft Teams com o [Monitor do Azure.](azure-monitor-manage.md) 
  
## <a name="basic-configuration"></a>Configuração básica

Essas propriedades representam a configuração mínima para que uma conta de dispositivo funcione com salas do Microsoft Teams. Sua conta de dispositivo pode exigir mais configuração.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Caixa de correio do Exchange (Exchange 2013 SP1 ou posterior, ou Exchange Online)  <br/> |A habilitação da conta com uma caixa de correio do Exchange oferece à conta do dispositivo a capacidade de receber e enviar solicitações de email e reunião, além de exibir um calendário de reuniões no dispositivo Salas do Microsoft Teams. A caixa de correio do Microsoft Teams Rooms deve ser uma caixa de correio de sala.  <br/> |
|O Skype for Business está habilitado  <br/> |O Skype for Business deve estar habilitado para usar vários recursos de conferência, como chamadas de vídeo, mensagens de voz e compartilhamento de tela. Há suporte para o Skype for Business Online e o Skype for Business Server.  <br/> |
|Habilitado por senha  <br/> |A conta do dispositivo deve ser habilitada com uma senha ou não pode ser autenticada com o Exchange ou o Skype for Business Server.  <br/> |
   
## <a name="advanced-configuration"></a>Configuração avançada

Embora as propriedades da configuração básica permitam que a conta do dispositivo seja configurada em um ambiente simples, é possível que seu ambiente tenha outras restrições em contas de diretório que devem ser atendidas para que as Salas do Microsoft Teams usem a conta do dispositivo com êxito.
  
|**Propriedade**|**Objetivo**|
|:-----|:-----|
|Autenticação baseada em certificado  <br/> |Os certificados podem ser necessários tanto para o Exchange quanto para o Skype for Business Server. Para implantar certificados, você pode carregá-los quando estiver conectado como Administrador.  <br/> |
   
A maneira mais fácil de configurar contas de dispositivo é configurá-las usando o Windows PowerShell remoto. A Microsoft [ forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de dispositivo ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de dispositivo compatíveis do Microsoft Teams Rooms.
  
Se você preferir usar a interface do usuário do Microsoft 365 ou do Office 365 em vez de cmdlets do Windows PowerShell, algumas etapas podem ser executadas manualmente. Veja [Como criar uma conta de dispositivo usando o Microsoft 365 ou o Office 365.](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)
  
## <a name="see-also"></a>Confira também

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

