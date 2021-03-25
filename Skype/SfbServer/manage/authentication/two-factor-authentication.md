---
title: Gerenciar autenticação de dois fatores no Skype for Business Server
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
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumo: Gerencie a autenticação de dois fatores no Skype for Business Server.'
ms.openlocfilehash: 8e8f665d824cd5f21cc2ca874668eba90bc97c4b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119540"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Gerenciar autenticação de dois fatores no Skype for Business Server
 
**Resumo:** Gerenciar a autenticação de dois fatores no Skype for Business Server.
  
A autenticação de dois fatores fornece segurança aprimorada, exigindo que os usuários forneçam duas formas de autenticação ou identificação, ou seja, uma combinação de nome de usuário/senha e um token ou certificado. Isso também é conhecido como "algo que você tem, algo que você sabe". 
  
Um exemplo típico de autenticação de dois fatores com um certificado é o uso de cartões inteligentes. Um cartão inteligente contém um certificado associado à conta de usuário e pode ser validado em relação às informações de usuário e certificado armazenadas em um servidor. Comparando as informações do usuário (nome de usuário e senha) com o certificado fornecido, o servidor valida as credenciais e autentica o usuário.
  
Considere os seguintes assuntos ao configurar um ambiente do Skype for Business Server para dar suporte à autenticação de dois fatores.
  
## <a name="client-support"></a>Suporte para Cliente

As Atualizações Cumulativas do Lync Server 2013: cliente de área de trabalho de julho de 2013 e o cliente skype for Business são os únicos clientes que atualmente suportam a autenticação de dois fatores.
  
## <a name="topology-requirements"></a>Requisitos de topologia

Os clientes são incentivados a implantar a autenticação de dois fatores usando o Skype for Business Server dedicado com Pools de Borda, Diretor e Usuário. Para habilitar a autenticação passiva para usuários, outros métodos de autenticação devem ser desabilitados para outras funções e serviços, incluindo o seguinte:
  
|**Tipo de configuração**|**Tipo de serviço**|**Função de servidor**|**Tipo de autenticação a ser desabilitado**|
|:-----|:-----|:-----|:-----|
|Serviço Web  <br/> |WebServer  <br/> |Diretor  <br/> |Kerberos, NTLM e Certificate  <br/> |
|Serviço Web  <br/> |WebServer  <br/> |Front-end  <br/> |Kerberos, NTLM e Certificate  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Borda  <br/> |Kerberos e NTLM  <br/> |
|Proxy  <br/> |Registrador  <br/> |Front-end  <br/> |Kerberos e NTLM  <br/> |
   
A menos que esses tipos de autenticação sejam desabilitados no nível de serviço, todas as outras versões do cliente não poderão entrar com êxito depois que a autenticação de dois fatores for habilitada em sua implantação.
  
## <a name="skype-for-business-service-discovery"></a>Descoberta do Serviço do Skype for Business

Os registros DNS usados por clientes internos e/ou externos para descobrir os serviços do Skype for Business devem ser configurados para resolver para um servidor do Skype for Business que não está habilitado para autenticação de dois fatores. Com essa configuração, os usuários dos Pools do Skype for Business que não estão habilitados para autenticação de dois fatores não serão necessários para inserir um PIN para autenticação, enquanto os usuários dos Pools do Skype for Business habilitados para autenticação de dois fatores serão obrigados a inserir seu PIN para autenticação.
  
## <a name="exchange-authentication"></a>Autenticação do Exchange

Os clientes que implantaram a autenticação de dois fatores para o Microsoft Exchange podem descobrir que determinados recursos no cliente estão indisponíveis. Isso é atualmente por design, pois o cliente skype for Business não dá suporte à autenticação de dois fatores para recursos que dependem da integração com o Exchange.
  
## <a name="contacts"></a>Contatos

Os usuários do Skype for Business que estão configurados para aproveitar o recurso de Armazenamento unificado de Contatos descobrirão que seus contatos não estão mais disponíveis depois de entrar com a autenticação de dois fatores.
  
Você deve usar o cmdlet **Invoke-CsUcsRollback** para remover contatos de usuário existentes do Armazenamento unificado de contatos e armazená-los no Skype for Business Server antes de habilitá-los.
  
## <a name="skill-search"></a>Pesquisa de Habilidades

Os clientes que configuraram o recurso pesquisa de habilidades em seu ambiente do Skype for Business descobrirão que esse recurso não funciona quando o Skype for Business está habilitado para autenticação de dois fatores. Isso é por design, pois o Microsoft SharePoint atualmente não dá suporte à autenticação de dois fatores.
  
## <a name="credentials"></a>Credenciais

Há várias considerações de implantação envolvendo credenciais salvas do Skype for Business que podem afetar os usuários configurados para usar a autenticação de dois fatores.
  
### <a name="deleting-saved-credentials"></a>Excluir credenciais salvas

Os usuários  devem usar a opção Excluir minhas informações de entrada no cliente skype for Business e excluir sua pasta de perfil SIP de %localappdata%\Microsoft\Office\15.0\Skype for Business antes de tentar entrar pela primeira vez usando a autenticação de dois fatores.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Com o método de autenticação Kerberos ou NTLM, as credenciais do Windows do usuário são usadas automaticamente para autenticação. Em uma implantação típica do Skype for Business Server em que Kerberos e/ou NTLM estão habilitados para autenticação, os usuários não devem ter que inserir suas credenciais sempre que entrarem.
  
Se os usuários não são solicitados intencionalmente a solicitar credenciais antes de serem solicitados a inserir seu PIN, a chave do Registro **DisableNTCredentials** pode ser configurada incorretamente em computadores cliente, possivelmente por meio da Política de Grupo.
  
Para impedir o prompt adicional de credenciais, crie a seguinte entrada do Registro na estação de trabalho local ou use o modelo administrativo do Skype for Business para aplicar a todos os usuários para um determinado pool usando a Política de Grupo:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Quando um usuário faz logor no Skype for Business pela primeira vez, o usuário é solicitado a salvar sua senha. Se selecionada, essa opção permite que o certificado de cliente do usuário seja armazenado no armazenamento de certificados pessoais e as credenciais do Windows do usuário sejam armazenadas no Gerenciador de Credenciais do computador local.
  
A configuração do Registro **savePassword** deve ser desabilitada quando o Skype for Business estiver configurado para dar suporte à autenticação de dois fatores. Para impedir que os usuários salvam suas senhas, altere a seguinte entrada do Registro na estação de trabalho local ou use o modelo administrativo do Skype for Business para aplicar a todos os usuários para um determinado pool usando a Política de Grupo:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>Reprodução de token do AD FS 2.0

O AD FS 2.0 fornece um recurso conhecido como detecção de repetição de token, pelo qual várias solicitações de token usando o mesmo token podem ser detectadas e descartadas. Quando esse recurso está habilitado, a detecção de repetição de token protege a integridade das solicitações de autenticação no perfil passivo WS-Federation e no perfil SAML WebSSO, fazendo com que o mesmo token nunca seja usado mais de uma vez.
  
Esse recurso deve ser habilitado em situações em que a segurança é uma preocupação muito alta, como ao usar quiosques. Para obter mais informações sobre a detecção de repetição de token, consulte [Best Practices for Secure Planning and Deployment of AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10)).
  
## <a name="external-user-access"></a>Acesso de usuário externo

A configuração de um Proxy ADFS ou Proxy Reverso para dar suporte à autenticação de dois fatores do Skype for Business de redes externas não é abordada nesses tópicos.
  
## <a name="see-also"></a>Confira também

[Configurar a autenticação de dois fatores no Skype for Business Server](configure-two-factor.md)
