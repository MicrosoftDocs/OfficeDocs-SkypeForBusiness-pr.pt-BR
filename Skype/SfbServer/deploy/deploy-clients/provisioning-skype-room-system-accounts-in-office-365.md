---
title: Provisionamento das contas do Sistema de Salas do Skype no Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leia este tópico para aprender sobre provisionamento de contas do Sistema de Salas do Skype no Office 365.
ms.openlocfilehash: 87643d04879888d59739c997e37108c6c7403101
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301537"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Provisionamento das contas do Sistema de Salas do Skype no Office 365
 
Leia este tópico para aprender sobre provisionamento de contas do Sistema de Salas do Skype no Office 365.
  
A seção a seguir aborda o provisionamento da conta do sistema de sala do Skype para um locatário do Office 365.
  
## <a name="office-365-prerequisites"></a>Pré-requisitos do Office 365

Seu locatário online deve cumprir os seguintes requisitos:
  
- O plano do Office 365 deve incluir o Skype for Business online plano 2 ou o Office 365 E1, E3 ou e5. <br/>Para obter detalhes sobre os planos do Skype for Business Online, consulte a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/jj822172.aspx).
    
- Seu locatário deve ter a funcionalidade de conferência do Skype for Business habilitada.
    
- Seu locatário deve ter o Exchange Online habilitado.   
    
- O administrador remoto do seu locatário deve ter o seguinte acesso PowerShell: 
    
  - Acesso PowerShell remoto do Exchange
    
  - Acesso do PowerShell remoto do Skype for Business Online
    
  - Módulo do Windows Azure Active Directory para Windows PowerShell para acessar o acesso a diretório do Office 365
    
Para a conta da Sala do Skype, o seguinte licenciamento é exigido:
  
- É necessária uma licença do Skype for Business online plano 2 ou Office 365 E1 ou E3 para habilitar reuniões do Skype.
    
- Para entitle a sala com a funcionalidade do Enterprise Voice para que a sala possa ser habilitada com um número de telefone, é necessário um plano 2 do Skype for Business online com a licença do sistema de telefone ou o Office 365 E5 (1).
    
- Se precisar de recursos de discagem de uma reunião, você precisará de uma conferência de áudio e uma licença do sistema de telefonia.  Se precisar de recursos de discagem de uma reunião, você precisará de um plano de chamada internacional ou doméstico e internacional. 
    
- Uma licença do Exchange Online não é necessária para a conta da Sala do Skype porque a conta deve ser configurada como uma conta de caixa postal de recursos. 
    
## <a name="provisioning-overview"></a>Visão geral do provisionamento

O diagrama a seguir fornece uma visão geral do fluxo de provisionamento da conta do sistema de sala do Skype no Office 365.
  
![Etapas do provisionamento do sistema de sala Skype para o O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar uma nova sala de conferência 

Você pode já ter uma caixa de correio de sala de recursos no Exchange que fornece o recurso de agendamento ou pode estar criando uma caixa de correio de recurso pela primeira vez para facilitar a implantação do sistema de sala do Skype. Em qualquer caso, você deve identificar uma conta de sala a ser usada em seu locatário. As seções de provisionamento do Exchange Online e do Skype for Business fornecem orientação para os dois tipos de conta. Por exemplo, digamos que você tenha as duas salas a seguir e queira implantar o sistema de salas da Skype para ambos:
  
- Conta existente da caixa de correio do recurso: confrm1@contoso.onmicrosoft.com
    
- Nova conta da caixa de correio do recurso: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Provisionamento do Exchange Online  

Primeiro, conecte-se ao PowerShell do Exchange Online seguindo as instruções no tópico [conectar-se ao PowerShell do Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Para definir uma conta de caixa de correio de sala de recursos existente para o sistema de sala do Skype, execute os seguintes comandos no PowerShell do Exchange Online:
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para criar uma nova conta de caixa de correio de recursos do Exchange para o sistema de sala do Skype, execute os seguintes comandos no PowerShell do Exchange Online:
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Os comandos anteriores configurados ou criar uma nova conta de caixa de correio de recursos do Exchange para o uso do sistema de sala do Skype habilitando a conta.
  
Depois de criar a caixa de correio, você pode usar o cmdlet Set-CalendarProcessing no PowerShell do Exchange Online para configurar a caixa de correio. Consulte as etapas de 3 a 6 sob Implantações locais da floresta única para obter mais detalhes.

## <a name="assigning-a-skype-for-business-online-license"></a>Atribuindo uma licença do Skype for Business Online 

Agora você pode atribuir uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3) usando o portal administrativo do Office 365 conforme descrito em [atribuir ou remover licenças para o Office 365 para empresas](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou no complemento do [Skype for Business. licenciamento](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Depois de atribuir uma licença do Skype for Business Online, você poderá se conectar e validar que a conta está ativa usando qualquer cliente Skype for Business.
  
## <a name="skype-for-business-online-provisioning"></a>Provisionamento do Skype for Business Online  

Após a criação e a habilitação da conta de caixa de correio da sala de recursos, conforme mostrado anteriormente, e você tiver licenciado a conta do Skype for Business Online, a conta será sincronizada da floresta do Exchange Online para a floresta do Skype for Business online usando o botão Floresta do Windows Azure Active Directory. As etapas a seguir são necessárias para configurar a conta do sistema de sala do Skype no pool do Skype for Business online. Essas etapas são as mesmas para uma conta de caixa de correio de recurso existente ou com uma conta recém-criada (confrm1 ou confrm2), como quando elas são habilitadas no Exchange Online, ambas as contas serão sincronizadas com o Skype for Business online da mesma maneira:
  
1. Crie uma sessão do PowerShell remoto. Observe que você precisará baixar o módulo do conector Skype for Business Online e o assistente de conexão do Microsoft Online Services e verificar se o seu computador está configurado. Para obter mais informações, consulte [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar uma conta do sistema de sala do Skype para o Skype for Business, execute o seguinte comando:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Você pode obter o endereço do RegistrarPool em que seus usuários do Skype for Business são hospedados em uma de suas contas existentes usando o seguinte comando para retornar essa propriedade:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>Expiração da senha

No Office 365, a política de expiração de senha padrão para todas as contas de usuário é de 90 dias, a menos que você configure uma política de expiração de senha diferente. Para contas do sistema de sala do Skype, você pode selecionar a configuração senha nunca expira com as etapas a seguir.
  
1. Crie uma sessão do Windows Azure Active Directory usando suas credenciais de administrador global do locatário. 
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Defina a configuração a senha nunca expira para a conta da sala do sistema de sala do Skype criada anteriormente usando o seguinte comando:
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obter mais informações, consulte [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Válida

Para a validação, você deve ser capaz de usar qualquer cliente Skype for Business para entrar na conta que você criou.

