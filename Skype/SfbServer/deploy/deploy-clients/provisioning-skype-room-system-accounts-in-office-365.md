---
title: Provisionando contas do Sistema de Sala do Skype no Microsoft 365 e no Office 365
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
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leia este tópico para saber mais sobre como provisionar contas do Sistema de Sala do Skype no Microsoft 365 ou no Office 365.
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820841"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Provisionando contas do Sistema de Sala do Skype no Microsoft 365 e no Office 365
 
Leia este tópico para saber mais sobre como provisionar contas do Sistema de Sala do Skype no Microsoft 365 ou no Office 365.
  
A seção a seguir aborda o provisionamento da conta do Sistema de Sala do Skype.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Pré-requisitos do Microsoft 365 e Office 365

Seu locatário online deve atender aos seguintes requisitos:
  
- O plano do Microsoft 365 ou Office 365 deve incluir o Skype for Business Online Plano 2 ou o Office 365 E1, E3 ou E5. <br/>Para obter detalhes sobre os Planos do Skype for Business Online, consulte a [Descrição do Serviço do Skype for Business Online.](https://technet.microsoft.com/library/jj822172.aspx)
    
- Seu locatário deve ter a funcionalidade de conferência do Skype for Business habilitada.
    
- Seu locatário deve ter o Exchange Online habilitado. 
    
- O administrador remoto do locatário deve ter o seguinte acesso ao PowerShell:
    
  - Acesso ao PowerShell Remoto do Exchange
    
  - Acesso ao PowerShell Remoto do Skype for Business Online
    
  - Módulo Do Windows Azure Active Directory para Windows PowerShell para acessar o diretório do Microsoft 365 ou Office 365
    
Para a conta da Sala do Skype, é necessário o seguinte licenciamento:
  
- Uma licença do Skype for Business Online Plano 2 ou Office 365 E1 ou E3 é necessária para habilitar as Reuniões do Skype.
    
- Para dar direito à sala com a funcionalidade do Enterprise Voice para que a sala possa ser habilitada com um número de telefone, é necessário ter o Skype for Business Online Plano 2 com a licença do Sistema de Telefonia ou o Office 365 E5 (1).
    
- Se precisar de recursos de discagem de uma reunião, você precisará de uma audioconferência e uma licença do Sistema de Telefonia.  Se precisar de recursos de discagem de uma reunião, você precisará de um Plano de Chamada doméstico ou doméstico e internacional. 
    
- Uma licença do Exchange Online não é necessária para a conta da Sala do Skype porque ela deve ser configurada como uma conta de caixa de correio de recurso.
    
## <a name="provisioning-overview"></a>Visão geral do provisionamento

O diagrama a seguir fornece uma visão geral do fluxo de provisionamento da conta do Sistema de Sala do Skype.
  
![Etapas de provisionamento do Sistema de Sala do Skype](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar uma nova sala de conferência

Você pode já ter uma caixa de correio de sala de recursos no Exchange que fornece o recurso de agendamento ou pode estar criando uma caixa de correio de recurso pela primeira vez para facilitar a implantação do Sistema de Sala do Skype. De qualquer forma, você deve identificar uma conta de sala a ser usada em seu locatário. As seções Provisão do Exchange Online e Provisão do Skype for Business fornecem orientações para ambos os tipos de contas. Por exemplo, digamos que você tenha as duas salas a seguir e gostaria de implantar o Sistema de Salas do Skype para ambas:
  
- Conta de Caixa de Correio de Recurso existente: confrm1@contoso.onmicrosoft.com
    
- Nova Conta de Caixa de Correio de Recurso: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Provisionamento do Exchange Online

Primeiro, conecte-se ao PowerShell do Exchange Online seguindo as instruções no tópico, [Conectar-se ao PowerShell do Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=396554)
  
Para definir uma conta de caixa de correio de sala de recursos existente para o Sistema de Sala do Skype, execute os seguintes comandos no PowerShell do Exchange Online:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para criar uma nova conta de caixa de correio de recursos do Exchange para o Sistema de Sala do Skype, execute os seguintes comandos no PowerShell do Exchange Online:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Os comandos anteriores configuram ou criam uma nova conta de caixa de correio de recursos do Exchange para uso do Sistema de Sala do Skype habilitando a conta.
  
Depois de criar a caixa de correio, você pode usar o cmdlet Set-CalendarProcessing no PowerShell do Exchange Online para configurar a caixa de correio. Consulte as etapas 3 a 6 em Implantações locais de floresta única para obter mais detalhes

## <a name="assigning-a-skype-for-business-online-license"></a>Atribuindo uma licença do Skype for Business Online

Agora você pode atribuir uma licença do Skype for Business Online (Plano 2) ou do Skype for Business Online (Plano 3) usando o portal administrativo do Microsoft 365 conforme descrito em Atribuir ou remover licenças do [Microsoft 365 para](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) empresas ou no licenciamento de complementos do Skype for [Business.](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7) 
  
Depois de atribuir uma licença para o Skype for Business Online, você poderá entrar e validar se a conta está ativa usando qualquer cliente do Skype for Business.
  
## <a name="skype-for-business-online-provisioning"></a>Provisionamento do Skype for Business Online

Depois que uma conta de caixa de correio de sala de recursos tiver sido criada e habilitada como mostrado anteriormente, e você tiver licenciado a conta para o Skype for Business Online, a conta será sincronizada da floresta do Exchange Online para a floresta do Skype for Business Online usando a floresta do Active Directory do Windows Azure. As etapas a seguir são necessárias para provisionar a conta do Sistema de Sala do Skype no pool do Skype for Business Online. Essas etapas são as mesmas para uma conta de caixa de correio de recurso existente ou uma conta recém-criada (confrm1 ou confrm2), pois depois de habilitadas no Exchange Online, ambas as contas serão sincronizadas com o Skype for Business Online da mesma maneira:
  
1. Crie uma sessão do PowerShell Remoto. Observe que você precisará baixar o Módulo conector do Skype for Business Online e o Assistente de Sign-In microsoft Online Services e certificar-se de que seu computador está configurado. Para obter mais informações, [consulte Configurar seu computador para o Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar uma conta do Sistema de Sala do Skype for Business, execute o seguinte comando:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Você pode obter o endereço RegistrarPool onde seus usuários do Skype for Business estão a partir de uma de suas contas existentes usando o seguinte comando para retornar essa propriedade:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>A MFA (Autenticação Multifatória) não é suportada para contas do Sistema de Sala do Skype. 

## <a name="password-expiration"></a>Expiração da senha

No Microsoft 365 ou Office 365, a política de expiração de senha padrão para todas as suas contas de usuário é de 90 dias, a menos que você configure uma política de expiração de senha diferente. Para contas do Sistema de Sala do Skype, você pode selecionar a configuração Senha nunca expira com as etapas a seguir.
  
1. Crie uma sessão do Windows Azure Active Directory usando suas credenciais de administrador global do locatário.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Definir a configuração Senha nunca expira para a conta de sala do Sistema de Sala do Skype criada anteriormente usando o seguinte comando:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obter mais informações, [consulte Configurar seu computador para o Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
  
## <a name="validate"></a>Validar

Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business para entrar na conta que você criou.

