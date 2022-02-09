---
title: Gerenciar configurações do Serviço Web em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumo: Gerencie as configurações do Serviço Web Skype for Business Server.'
ms.openlocfilehash: 29f3c3a4aae8a444c9d247b39d6c3fdfcd4b1c9a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411644"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Gerenciar configurações do Serviço Web em Skype for Business Server
 
**Resumo:** Gerenciar configurações do Serviço Web em Skype for Business Server.
  
Você pode usar a **página serviço Web** para configurar os métodos de autenticação para acessar Skype for Business Server web e serviços Web relacionados.
  
Siga estas etapas para criar uma nova política de Serviço Web.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Para criar novas configurações de serviço Web

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.
    
4. Na página **Serviço Web** , clique em **Novo** e faça um dos seguintes:
    
   - Para configurar o Serviço Web para um site, clique em **Configuração do site**. Em **Selecionar um Site**, clique no site ao qual a política de Serviço Web será aplicada a um site e clique em **OK**.
    
   - Para configurar o Serviço Web para um pool, clique em **Configuração do pool**. Em **Selecionar um Serviço**, clique no serviço ao qual a política de Serviço Web será aplicada e clique em **OK**. 
    
5. Em **Nova Configuração do Serviço Web**, em **Autenticação Windows,** selecione **Negociar**, **Autenticação Windows integrada** ou **Nenhum**.
    
6. Selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes do e suporte em seu ambiente:
    
   - **Habilitar Autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.
    
   - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.
    
   - **Habilitar download da cadeia de certificados** para que os servidores com um certificado de autenticação baixem a cadeia de certificados para esse certificado.
    
7. Clique em **Confirmar**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Modificar configurações existentes do Serviço Web

Você pode usar a **página serviço Web** para configurar os métodos de autenticação para acessar Skype for Business Server web e serviços Web relacionados.
  
Execute estas etapas para modificar uma política de Serviço Web existente.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Para modificar as configurações de serviço Web existentes

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.
    
4. Na página **Serviço Web**, clique em uma configuração, em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Configuração do Serviço Web**, em **Autenticação do Windows Integrada**, selecione **Negociar**, **NTLM** ou **Nenhum**.
    
6. Selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes do e suporte em seu ambiente:
    
   - **Habilitar Autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.
    
   - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.
    
   - **Habilitar download da cadeia de certificados** para que os servidores com um certificado de autenticação baixem a cadeia de certificados para esse certificado.
    
7. Clique em **Confirmar**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Excluir configurações existentes do Serviço Web

Siga estas etapas para excluir as configurações do serviço Web.
  
### <a name="to-delete-web-service-configuration-settings"></a>Para excluir as configurações do serviço Web

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.
    
4. Na página **Serviço Web**, e no campo de pesquisa, digite todo ou parte do nome da política que você deseja excluir.
    
5. Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.
    
6. Clique em **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Excluir a Configuração do Serviço Web Configurações usando Windows PowerShell Cmdlets

Você pode excluir as configurações do serviço Web usando o Windows PowerShell e o cmdlet **Remove-CsWebServiceConfiguration**. Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Administração do Microsoft Lync Remote PowerShell](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Para excluir um conjunto específico de definições de configuração do serviço da Web

- O seguinte comando remove as configurações de segurança do Serviço da Web aplicadas ao local Redmond:
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Para excluir todas as configurações do serviço Web aplicadas ao escopo do site

O seguinte comando remove todas as configurações de segurança do Serviço da Web aplicadas ao escopo do serviço:
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Para excluir todas as configurações do serviço Web que permitem autenticação de certificados

O seguinte comando remove todas as configurações de segurança do Serviço da Web que permitem o uso de autenticação de certificados:
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Para obter detalhes, [consulte Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
