---
title: Gerenciar definições de configuração do Serviço Web no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumo: Gerenciar definições de configuração do Serviço Web no Skype for Business Server.'
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806491"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Gerenciar definições de configuração do Serviço Web no Skype for Business Server
 
**Resumo:** Gerenciar definições de configuração do Serviço Web no Skype for Business Server.
  
Você pode usar a **página Serviço Web** para configurar os métodos de autenticação para acessar servidores Web e Serviços Web relacionados ao Skype for Business Server.
  
Siga estas etapas para criar uma nova política de Serviço Web.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Para criar novas definições de configuração do serviço Web

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.
    
4. Na página **Serviço web,** clique em **Novo** e, em seguida, faça um dos seguintes:
    
   - Para configurar o Serviço Web para um site, clique em **Configuração do site.** Em **Selecionar um Site,** clique no site ao qual a política de Serviço Web será aplicada a um site e clique em **OK.**
    
   - Para configurar o Serviço Web para um pool, clique em **Configuração de pool.** Em **Selecionar um Serviço,** clique no serviço ao qual a política de Serviço Web será aplicada e clique em **OK.** 
    
5. In **New Web Service Setting**, in Integrated Windows **authentication**, select **Negotiate**, Integrated **Windows authentication**, or **None**.
    
6. Selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes do e suporte em seu ambiente:
    
   - **Habilitar Autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.
    
   - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.
    
   - **Habilitar download da cadeia de certificados** para que os servidores com um certificado de autenticação baixem a cadeia de certificados para esse certificado.
    
7. Clique em **Confirmar**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Modificar definições de configuração existentes do Serviço Web

Você pode usar a **página Serviço Web** para configurar os métodos de autenticação para acessar servidores Web e Serviços Web relacionados ao Skype for Business Server.
  
Execute estas etapas para modificar uma política de Serviço Web existente.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Para modificar as definições de configuração existentes do serviço Web

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.
    
4. Na página **Serviço Web**, clique em uma configuração, em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Configuração do Serviço Web**, em **Autenticação do Windows Integrada**, selecione **Negociar**, **NTLM** ou **Nenhum**.
    
6. Selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes do e suporte em seu ambiente:
    
   - **Habilitar Autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.
    
   - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.
    
   - **Habilitar download da cadeia de certificados** para que os servidores com um certificado de autenticação baixem a cadeia de certificados para esse certificado.
    
7. Clique em **Confirmar**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Excluir definições de configuração existentes do Serviço Web

Siga estas etapas para excluir as definições de configuração do serviço Web.
  
### <a name="to-delete-web-service-configuration-settings"></a>Para excluir definições de configuração do serviço Web

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.
    
4. Na página **Serviço Web**, e no campo de pesquisa, digite todo ou parte do nome da política que você deseja excluir.
    
5. Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.
    
6. Clique em **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Excluindo definições de configuração do serviço Web usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração do serviço Web usando o Windows PowerShell e o cmdlet **Remove-CsWebServiceConfiguration.** Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Para excluir um conjunto específico de definições de configuração do serviço da Web

- O seguinte comando remove as configurações de segurança do Serviço da Web aplicadas ao local Redmond:
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Para excluir todas as definições de configuração do serviço Web aplicadas ao escopo do site

O seguinte comando remove todas as configurações de segurança do Serviço da Web aplicadas ao escopo do serviço:
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Para excluir todas as definições de configuração do serviço Web que permitem a autenticação de certificado

O seguinte comando remove todas as configurações de segurança do Serviço da Web que permitem o uso de autenticação de certificados:
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Para obter detalhes, [consulte Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  

