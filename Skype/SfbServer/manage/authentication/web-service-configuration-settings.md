---
title: Gerenciar definições de configuração do serviço Web no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumo: Gerencie definições de configuração do serviço Web no Skype para Business Server.'
ms.openlocfilehash: 53d709c9964a665c97ba809ca6f40dceb0be137b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884101"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Gerenciar definições de configuração do serviço Web no Skype para Business Server
 
**Resumo:** Gerencie definições de configuração do serviço Web no Skype para Business Server.
  
Você pode usar a página **Serviço Web** para configurar os métodos de autenticação para acessar o Skype para Business Server relacionados servidores web e serviços da Web.
  
Siga estas etapas para criar a nova política de Web Service.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Para criar novas definições de configuração de serviço da Web

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
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

Você pode usar a página **Serviço Web** para configurar os métodos de autenticação para acessar o Skype para Business Server relacionados servidores web e serviços da Web.
  
Execute estas etapas para modificar uma política de Serviço Web existente.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Para modificar definições de configuração de Serviço da Web

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
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

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.
    
4. Na página **Serviço da Web**, e no campo de pesquisa, digite todo ou parte do nome da política que você deseja excluir.
    
5. Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.
    
6. Clique em **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>A exclusão de definições de configuração do serviço Web usando Cmdlets do Windows PowerShell

Você pode excluir as definições de configuração do serviço web usando o Windows PowerShell e o cmdlet **Remove-CsWebServiceConfiguration** . Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Para excluir um conjunto específico de definições de configuração do serviço da Web

- O seguinte comando remove as configurações de segurança do Serviço da Web aplicadas ao local Redmond:
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Para excluir todas as definições de configuração do serviço da Web aplicadas ao escopo local

O seguinte comando remove todas as configurações de segurança do Serviço da Web aplicadas ao escopo do serviço:
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Para excluir todas as definições de configuração do Serviço da Web que permitem a autenticação de certificado

O seguinte comando remove todas as configurações de segurança do Serviço da Web que permitem o uso de autenticação de certificados:
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Para obter detalhes, consulte [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  

