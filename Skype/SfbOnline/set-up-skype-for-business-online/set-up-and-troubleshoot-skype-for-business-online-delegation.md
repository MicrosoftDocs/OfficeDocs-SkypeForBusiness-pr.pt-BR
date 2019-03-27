---
title: Configurar e solucionar problemas de delegação do Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Este artigo explica como configurar e solucionar problemas Skype para delegação Business Online. Este artigo fornece orientações para as etapas de solução de problemas, práticas recomendadas e recomendações de instalação.
ms.openlocfilehash: 450aee07691a007b976aafffc05d34c3e7ef85f2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887831"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurar e solucionar problemas de delegação do Skype for Business Online

Este artigo explica como configurar e solucionar problemas Skype para delegação Business Online. Este artigo fornece orientações para as etapas de solução de problemas, práticas recomendadas e recomendações de instalação.
  
## <a name="guidelines-and-requirements"></a>Requisitos e diretrizes

### <a name="guidelines-for-delegation"></a>Diretrizes para delegação

Configurando e instalando a delegação funcione corretamente dependem seguir estas diretrizes:
  
- Você deve estar usando o Skype para negócios 2015 completa do cliente com as atualizações mais recentes ou o Skype para negócios 2016 completa do cliente.
    
- Você deve estar usando o cliente do Outlook 2013 com as atualizações mais recentes ou o cliente Outlook 2016.
    
- Certifique-se de que o delegator e o representante computadores têm um perfil de email do Outlook que é o principal ou o perfil padrão. Se o perfil de email deve conter apenas uma conta.
    
- Skype para negócios para o delegator e o delegado deve ser usuários Online. Além disso, as Exchange Server caixas de correio para cada conta deverá estar Online ou ambos ser no local.
    
- Delegator tanto o delegado devem estar usando a mesma versão principal do Outlook.
    
- O valor do atributo **EnableExchangeDelegateSync** deve ser definido como **true** na diretiva do cliente. Você pode verificar esta configuração, executando o cmdlet **Get-CSClientPolicy** no Skype para o módulo de PowerShell Online de negócios.
    
- O delegator e o delegado devem estar conectados ao Skype para negócios e do Outlook ao mesmo tempo em diferentes estações de trabalho.
    
- Caixas de correio compartilhadas não são suportadas para Skype para delegação Business Online. Isso ocorre porque a caixa de correio compartilhada não tem a lista de controle de acesso (ACL) **sendonbehalf** .
    
### <a name="skype-for-business-client-version-support"></a>Skype para suporte de versão do cliente de negócios

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype para negócios básicos do cliente**| Não suportado |Não suportado
|**Skype for Business 2015**|Compatível | Compatível|
|**Skype para 2016 de negócios**|Compatível | Compatível|

   
### <a name="licensing-requirements"></a>Requisitos de licenciamento

**Cenário de licenciamento corporativo E3**

|**Licença**|**Clientes**|**Observações**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype para negócios 2015) usados com o Outlook 2013 ou 2016 do Outlook  <br/> Skype para 2016 corporativos usados com o Outlook 2013 ou 2016 do Outlook  <br/> |Skype para básicos de negócios do cliente não oferece suporte a delegação.  <br/> Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.  <br/> |
|Enterprise E3 com o sistema de telefone do Office 365 + Office 365 xCalling plano  <br/> |Lync 2013 (Skype para negócios 2015) usados com o Outlook 2013 ou 2016 do Outlook  <br/> Skype para 2016 corporativos usados com o Outlook 2013 ou 2016 do Outlook  <br/> Lync para Mac 2011  <br/> |Skype para básicos de negócios do cliente não oferece suporte a delegação.  <br/> Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.  <br/> |
   
**Cenário de licenciamento E5 da empresa**

|**Licença**|**Clientes**|**Observações**|
|:-----|:-----|:-----|
|E5 da empresa  <br/> |Lync 2013 (Skype para negócios 2015) usados com o Outlook 2013 ou 2016 do Outlook.  <br/> Skype para 2016 corporativos usados com o Outlook 2013 ou 2016 do Outlook  <br/> |Skype para básicos de negócios do cliente não oferece suporte a delegação.  <br/> Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.  <br/> |
|Enterprise E5 plus plano de chamada do Office 365  <br/> |Skype para negócios para Mac 2016  <br/> Lync 2013 (Skype para negócios 2015) usados com o Outlook 2013 ou 2016 do Outlook  <br/> Skype para 2016 corporativos usados com o Outlook 2013 ou 2016 do Outlook  <br/> Lync para Mac 2011  <br/> |Skype para básicos de negócios do cliente não oferece suporte a delegação.  <br/> Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurar e verificar a delegação

Para configurar o Skype para delegação Business Online, siga estas etapas:
  
### <a name="for-windows-clients"></a>Para clientes Windows

 **Guia de encaminhamento de chamadas**
  
1. Selecione **Ferramentas** > **Opções** > **configurações de encaminhamento de chamadas**.
    
2. Selecione **Editar Meus membros representantes**.
    
3. Selecione **Adicionar**, selecione o representante que você deseja adicionar e selecione **Okey**.
    
 **Nenhuma guia encaminhamento de chamadas**
  
1. No Outlook, selecione o **arquivo** > **Configurações de conta** > **Acesso delegado** > **Add**.
    
2. Localize e, em seguida, adicione o nome da pessoa que vai ser delegado.
    
3. Selecione o menu **calendário** e selecione **Editor (pode ler, criar e modificar itens)**.
    
### <a name="for-mac-clients---lync"></a>Clientes Mac - Lync

 **Guia de encaminhamento de chamadas**
  
- Se o cliente não tem uma guia **Encaminhamento de chamadas** que tenha o link **Editar Meus membros representantes** e representante está localizado em um computador Mac, representante deve entrar em um computador baseado no Windows para configurar a delegação. Isso ocorre porque os clientes Mac não podem fazer conexões MAPI e isso é um requisito para estabelecer Skype para delegação de negócios do Outlook.
    
### <a name="verify-success"></a>Verificar o sucesso

Se a instalação for bem-sucedida, o representante verá **você foi adicionado como um representante < Name>** a mensagem e também que o grupo de **pessoas para as quais gerenciar chamadas** é criado. Representante verá que o grupo de **delegados** é criado.
  
> [!NOTE]
> Permissões de delegação normalmente aparecem em até 30 minutos do processo de instalação. No entanto, esse processo pode levar até 24 horas para ser concluída. 
  
## <a name="troubleshooting"></a>Solução de problemas

### <a name="common-issues"></a>Problemas comuns

- > **Problema 1** A entrada de representante continua aparecem no grupo de **pessoas para as quais gerenciar chamadas** após a delegator tiver removido o representante do cliente do Outlook.
    
  - > **Solução 1** Na Skype para o cliente de negócios, o representante do grupo de **representantes** do mouse em e selecione **Remover do grupo**.
    
- > **Problema 2** Depois que o acesso de representante for concedido por meio do cliente do Outlook, nem a mensagem de confirmação nem o grupo de **pessoas para as quais gerenciar chamadas** aparecem para o representante.
    
  - > **Resolução 2** Remover a delegação de cliente do Outlook, aguarde cerca de 15 minutos para replicação e adicione novamente o delegado.
    
### <a name="other-common-issues"></a>Outros problemas comuns

- Delegação não funciona se o limite dos 25 delegantes e 25 representantes é excedido.
    
- Não há suporte para o Skype para básicos de negócios do cliente.
    
    > [!NOTE]
    > Se você instalar o Skype para básicos de negócios do cliente, ele removerá e interromper a delegação. 
  
- Se o valor de **Status de MAPI** não for **Okey**, certifique-se de que coincidem com os valores de **SIP** e **SMTP** .
    
    > [!NOTE]
    > Pode levar alguns minutos para que o status MAPI exibir como **Okey** após iniciar primeiro Skype para negócios e Outlook.
  
- Criando um grupo de segurança e adicionar permissões de delegação para esse grupo de segurança não não suportado.
    
- MAPI não está disponível. Consulte a [mensagem de erro "MAPI indisponível" no Skype para 2016 de negócios do cliente](https://support.microsoft.com/en-us/help/3147130).
    
- A caixa de correio do Exchange Online não está acessível através do Skype para o cliente de negócios. Se isso ocorrer, execute o [teste de conectividade do Outlook](https://testconnectivity.microsoft.com/) para certificar-se de que ele passa.
    
## <a name="related-topics"></a>Tópicos relacionados
[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
