---
title: Provisionamento de contas do sistema de salas do Skype no Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leia este tópico para saber mais sobre o provisionamento de contas do sistema de salas do Skype no Office 365.
ms.openlocfilehash: 141c833bcbdd744a7577c0762cb8ba55dd3d5c54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037721"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Provisionamento de contas do sistema de salas do Skype no Office 365
 
Leia este tópico para saber mais sobre o provisionamento de contas do sistema de salas do Skype no Office 365.
  
A seção a seguir abrange o provisionamento de contas do sistema de salas do Skype para um locatário do Office 365.
  
## <a name="office-365-prerequisites"></a>Pré-requisitos do Office 365

Seu locatário online deve atender aos seguintes requisitos:
  
- O plano do Office 365 deve incluir o Skype for Business online plano 2 ou o Office 365 E1, E3 ou e5. <br/>Para obter detalhes sobre os planos do Skype for Business Online, consulte a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/jj822172.aspx).
    
- Seu locatário deve ter o recurso de conferência do Skype for Business habilitado.
    
- Seu locatário deve ter o Exchange Online habilitado. 
    
- O administrador remoto do locatário deve ter o seguinte acesso do PowerShell:
    
  - Acesso do PowerShell remoto do Exchange
    
  - Acesso do PowerShell remoto do Skype for Business Online
    
  - Módulo do Windows Azure Active Directory para Windows PowerShell para acessar o acesso ao diretório do Office 365
    
Para a conta de sala do Skype, é necessário o seguinte:
  
- Uma licença do Skype for Business online plano 2 ou Office 365 E1 ou E3 é necessária para habilitar reuniões do Skype.
    
- Para entitle a sala com o recurso Enterprise Voice para que a sala possa ser habilitada com um número de telefone, o Skype for Business online plano 2 com a licença do sistema de telefonia ou o Office 365 E5 é necessário (1).
    
- Se você precisar de recursos de discagem de uma reunião, precisará de uma conferência de áudio e de sistema de telefonia.  Se você precisar de recursos de discagem de uma reunião, será necessário um plano de chamadas domésticas ou domésticas e internacionais. 
    
- Uma licença do Exchange Online não é necessária para a conta da sala do Skype porque a conta deve ser configurada como uma conta de caixa de correio de recurso.
    
## <a name="provisioning-overview"></a>Visão geral do provisionamento

O diagrama a seguir fornece uma visão geral do fluxo de provisionamento da conta do sistema de salas do Skype no Office 365.
  
![Etapas de provisionamento do sistema de salas do Skype para o O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar uma nova sala de conferência

Talvez você já tenha uma caixa de correio de sala de recursos no Exchange que forneça o recurso de agendamento ou que você esteja criando uma caixa de correio de recurso pela primeira vez para facilitar a implantação do sistema de salas do Skype. Em qualquer caso, você deve identificar uma conta de sala a ser usada em seu locatário. As seções de provisionamento do Exchange Online e do Skype for Business oferecem orientações para os dois tipos de contas. Por exemplo, digamos que você tenha as duas salas a seguir e queira implantar o sistema de salas do Skype para ambos:
  
- Conta de caixa de correio de recurso existente: confrm1@contoso.onmicrosoft.com
    
- Nova conta de caixa de correio de recurso: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Provisionamento do Exchange Online

Primeiro, conecte-se ao PowerShell do Exchange Online seguindo as instruções no tópico, [Conecte-se ao PowerShell do Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Para definir uma conta de caixa de correio de sala de recursos existente para o sistema de salas do Skype, execute os seguintes comandos no PowerShell do Exchange Online:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para criar uma nova conta de caixa de correio de recursos do Exchange para o sistema de salas do Skype, execute os seguintes comandos no PowerShell do Exchange Online:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Os comandos anteriores configurar ou criar uma nova conta de caixa de correio de recurso do Exchange para o uso do sistema de salas do Skype habilitando a conta.
  
Após criar a caixa de correio, você pode usar o cmdlet Set-CalendarProcessing no PowerShell do Exchange Online para configurar a caixa de correio. Consulte as etapas de 3 a 6 sob implantações locais da floresta única para obter mais detalhes

## <a name="assigning-a-skype-for-business-online-license"></a>Atribuindo uma licença do Skype for Business Online

Agora você pode atribuir uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3) usando o portal administrativo do Office 365, conforme descrito em [assign or Remove licenses for Office 365 for Business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou no [Skype for Business Add-on Licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Após atribuir uma licença para o Skype for Business Online, você poderá entrar e validar que a conta está ativa usando qualquer cliente Skype for Business.
  
## <a name="skype-for-business-online-provisioning"></a>Provisionamento do Skype for Business Online

Após uma conta de caixa de correio de sala de recursos ter sido criada e habilitada, conforme mostrado anteriormente, e você tiver licenciado a conta do Skype for Business Online, a conta será sincronizada a partir da floresta do Exchange Online para a floresta do Skype for Business online usando o Floresta do Active Directory do Windows Azure. As etapas a seguir são necessárias para provisionar a conta do sistema de salas do Skype no pool do Skype for Business online. Essas etapas são as mesmas para uma conta de caixa de correio de recurso existente ou para uma conta recentemente criada (confrm1 ou confrm2), porque depois de habilitadas no Exchange Online, ambas as contas serão sincronizadas com o Skype for Business online da mesma maneira:
  
1. Criar uma sessão remota do PowerShell. Observe que você precisará baixar o módulo do conector do Skype for Business Online e o assistente de conexão do Microsoft Online Services e verificar se o computador está configurado. Para obter mais informações, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar uma conta do sistema de salas do Skype para o Skype for Business, execute o seguinte comando:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Você pode obter o endereço do RegistrarPool em que seus usuários do Skype for Business são hospedados em uma de suas contas existentes usando o seguinte comando para retornar essa propriedade:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>A MFA (autenticação multifator) não tem suporte para contas do sistema de salas do Skype. 

## <a name="password-expiration"></a>Expiração da senha

No Office 365, a política de expiração de senha padrão para todas as suas contas de usuário é de 90 dias, a menos que você configure uma política de expiração de senha diferente. Para contas do sistema de salas do Skype, você pode selecionar a configuração a senha nunca expira com as etapas a seguir.
  
1. Crie uma sessão do Windows Azure Active Directory usando suas credenciais de administrador global do locatário.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Defina a configuração a senha nunca expira para a conta de sala do sistema de salas do Skype criada anteriormente usando o seguinte comando:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obter mais informações, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Validar

Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business para entrar na conta que você criou.

