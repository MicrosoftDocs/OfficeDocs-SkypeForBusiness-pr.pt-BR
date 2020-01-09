---
title: Gerenciar configurações de serviço Web no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumo: gerenciar configurações de serviço Web no Skype for Business Server.'
ms.openlocfilehash: 383b85e156dfdbc6af7606da49d4cf89bf655698
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991926"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Gerenciar configurações de serviço Web no Skype for Business Server
 
**Resumo:** Gerenciar configurações de serviço Web no Skype for Business Server.
  
Você pode usar a página **serviço Web** para configurar os métodos de autenticação para acessar servidores Web e serviços Web relacionados ao Skype for Business Server.
  
Siga estas etapas para criar a nova política de Web Service.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Para criar novas definições de configuração de serviço da Web

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.
    
4. Na página **Serviço da Web**, clique em **Novo** e faça um dos seguintes:
    
   - Para configurar o Serviço da Web para um site, clique em **Configuração do site**. Em **Selecionar um site**, clique em um site no qual a política de Serviço da Web será aplicada e clique em **OK**.
    
   - Para configurar o Serviço da Web para um pool, clique em **Configuração do pool**. Em **Selecionar um Serviço**, clique no serviço no qual a política de Serviço da Web será aplicada e clique em **OK**. 
    
5. Em **Nova configuração do Serviço da Web**, em **Autenticação integrada do Windows**, selecione **Negociar**, **Autenticação integrada do Windows** ou **Nenhum**.
    
6. Selecione um ou mais dos seguintes dependendo das capacidades dos clientes e do suporte no seu ambiente:
    
   - **Habilitar autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.
    
   - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.
    
   - **Habilitar download da cadeia de certificados** para que os servidores sejam apresentados com um download de certificado de autenticação da cadeia de certificados para aquele certificado.
    
7. Clique em **Confirmar**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Modificar definições de configuração de Serviço da Web

Você pode usar a página **serviço Web** para configurar os métodos de autenticação para acessar servidores Web e serviços Web relacionados ao Skype for Business Server.
  
Execute estas etapas para modificar uma política de Serviço Web existente.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Para modificar definições de configuração de Serviço da Web

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.
    
4. Na página **Serviço da Web**, clique em uma configuração, em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Configuração do Serviço da Web**, em **Autenticação do Windows Integrada**, selecione **Negociar**, **NTLM** ou **Nenhum**.
    
6. Selecione um ou mais dos seguintes dependendo das capacidades dos clientes e do suporte no seu ambiente:
    
   - **Habilitar autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.
    
   - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.
    
   - **Habilitar download da cadeia de certificados** para que os servidores sejam apresentados com um download de certificado de autenticação da cadeia de certificados para aquele certificado.
    
7. Clique em **Confirmar**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Excluir definições de configuração de Serviço da Web

Siga estas etapas para excluir definições de configuração do serviço da web.
  
### <a name="to-delete-web-service-configuration-settings"></a>Para excluir definições de configuração de serviço da Web

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.
    
4. Na página **Serviço da Web**, e no campo de pesquisa, digite todo ou parte do nome da política que você deseja excluir.
    
5. Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.
    
6. Clique em **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Excluindo configurações de serviço Web usando cmdlets do Windows PowerShell

Você pode excluir as configurações de serviço Web usando o Windows PowerShell e o cmdlet **Remove-CsWebServiceConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Para excluir um conjunto específico de definições de configuração do serviço da Web

- O seguinte comando remove as configurações de segurança do Serviço da Web aplicadas ao local Redmond:
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Para excluir todas as definições de configuração do serviço da Web aplicadas ao escopo local

O seguinte comando remove todas as configurações de segurança do Serviço da Web aplicadas ao escopo do serviço:
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Para excluir todas as definições de configuração do Serviço da Web que permitem a autenticação de certificado

O seguinte comando remove todas as configurações de segurança do Serviço da Web que permitem o uso de autenticação de certificados:
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Para obter detalhes, consulte [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  

