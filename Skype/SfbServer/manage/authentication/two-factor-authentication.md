---
title: Gerenciar a autenticação de dois fatores no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumo: gerenciar a autenticação de dois fatores no Skype for Business Server.'
ms.openlocfilehash: ccda6795fa5033c792c293701d951e3111666e82
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297558"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Gerenciar a autenticação de dois fatores no Skype for Business Server
 
**Resumo:** Gerenciar a autenticação de dois fatores no Skype for Business Server.
  
A autenticação de dois fatores oferece maior segurança ao exigir que os usuários forneçam duas formas de autenticação ou identificação, ou seja, uma combinação de nome de usuário/senha e um token ou certificado. Isso também é conhecido como "algo que você tem, algo que você conhece". 
  
Um exemplo típico da autenticação de dois fatores com um certificado é o uso de cartões inteligentes. Um cartão inteligente contém um certificado associado à conta do usuário e pode ser validado com as informações e certificado e usuário que estão armazenadas em um servidor. Ao comparar as informações do usuário (nome do usuário e senha) ao certificado fornecido, o servidor valida as credenciais e autentica o usuário.
  
Considere os seguintes assuntos ao configurar um ambiente do Skype for Business Server para dar suporte à autenticação de dois fatores.
  
## <a name="client-support"></a>Suporte de Cliente

As atualizações cumulativas do Lync Server 2013: cliente de área de trabalho do 2013 de julho e do cliente Skype for Business são os únicos clientes que atualmente dão suporte à autenticação de dois fatores.
  
## <a name="topology-requirements"></a>Requisitos de topologia

Os clientes são altamente incentivados a implantar a autenticação de dois fatores usando o Skype for Business Server dedicado com o Edge, o director e os pools de usuários. Para habilitar a autenticação passiva para usuários, é necessário desabilitar outros métodos de autenticação para outras funções e serviços, tais como:
  
|**Tipo de configuração**|**Tipo de serviço**|**Função do servidor**|**Tipo de autenticação a ser desabilitada**|
|:-----|:-----|:-----|:-----|
|Serviço Web  <br/> |WebServer  <br/> |Diretor  <br/> |Kerberos, NTLM e Certificado  <br/> |
|Serviço Web  <br/> |WebServer  <br/> |Front-End  <br/> |Kerberos, NTLM e Certificado  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Borda  <br/> |Kerberos e NTLM  <br/> |
|Proxy  <br/> |Registrador  <br/> |Front-End  <br/> |Kerberos e NTLM  <br/> |
   
A não ser que esses tipos de autenticação estejam desabilitados no nível de serviço, todas as outras versões do cliente não conseguirão se conectar enquanto a autenticação de dois fatores estiver habilitada em sua implantação.
  
## <a name="skype-for-business-service-discovery"></a>Descoberta de Serviços do Skype for Business

Os registros DNS usados por clientes internos e/ou externos para descobrir os serviços do Skype for Business devem ser configurados para resolver para um servidor do Skype for Business que não esteja habilitado para autenticação de dois fatores. Com essa configuração, os usuários de pools do Skype for Business que não estão habilitados para a autenticação de dois fatores não serão necessários para inserir um PIN para autenticação, enquanto os usuários de pools do Skype for Business habilitados para a autenticação de dois fatores serão obrigatório para inserir o PIN para autenticação.
  
## <a name="exchange-authentication"></a>Autenticação do Exchange

Os clientes que implantaram a autenticação de dois fatores para o Microsoft Exchange podem descobrir que determinados recursos do cliente não estão disponíveis. Isso, no momento, é o design, pois o cliente Skype for Business não oferece suporte à autenticação de dois fatores para recursos que dependem da integração do Exchange.
  
## <a name="contacts"></a>Contatos

Os usuários do Skype for Business que estiverem configurados para aproveitar o recurso de repositório de contatos unificado acharão que seus contatos não estarão mais disponíveis depois de entrar com a autenticação de dois fatores.
  
Você deve usar o cmdlet **Invoke-CsUcsRollback** para remover os contatos do usuário existentes do repositório de contatos unificado e armazená-los no Skype for Business Server antes de habilitar a autenticação de dois fatores.
  
## <a name="skill-search"></a>Pesquisa de Habilidades

Os clientes que configuraram o recurso de pesquisa de habilidades no ambiente do Skype for Business acharão que esse recurso não funciona quando o Skype for Business estiver habilitado para autenticação de dois fatores. Isso ocorre devido ao projeto, já que o Microsoft SharePoint não é compatível com a autenticação de dois fatores.
  
## <a name="credentials"></a>Credenciais

Há várias considerações de implantação envolvendo as credenciais do Skype for Business salvas, que podem afetar os usuários configurados para usar a autenticação de dois fatores.
  
### <a name="deleting-saved-credentials"></a>Exclusão de Credenciais Salvas

Os usuários devem usar a opção **excluir minhas informações de entrada** no cliente Skype for Business e excluir a pasta de perfil SIP do%LocalAppData%\Microsoft\Office\15.0\Skype for Business antes de tentar se conectar pela primeira vez usando dois fatores autenticação.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Com o método de autenticação Kerberos ou NTLM, as credenciais do Windows do usuário são usadas automaticamente para autenticação. Em uma implantação típica do Skype for Business Server na qual Kerberos e/ou NTLM está habilitado para autenticação, os usuários não devem digitar as credenciais toda vez que entrarem.
  
Se as credenciais dos usuários forem inadvertidamente solicitadas antes de ser necessário informar o PIN, a chave de registro **DisableNTCredentials** pode estar configurada por engano nos computadores clientes, possivelmente através de uma Política de Grupo.
  
Para impedir o prompt adicional de credenciais, crie a seguinte entrada do registro na estação de trabalho local ou use o modelo administrativo do Skype for Business para aplicar a todos os usuários de um determinado pool usando a política de Grupo:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Quando um usuário entrar no Skype for Business pela primeira vez, o usuário será solicitado a salvar sua senha. Se selecionada, essa opção permite que o certificado de cliente do usuário seja armazenado no repositório de certificados pessoal e as credenciais do Windows do usuário sejam armazenadas no Gerenciador de credenciais do computador local.
  
A configuração do registro **SavePassword** deve ser desabilitada quando o Skype for Business for configurado para dar suporte à autenticação de dois fatores. Para impedir que os usuários salvem suas senhas, altere a seguinte entrada do registro na estação de trabalho local ou use o modelo administrativo do Skype for Business para aplicar a todos os usuários de um determinado pool usando a política de Grupo:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 Token Replay

O AD FS 2.0 oferece um recurso chamado detecção de repetição de token, pelo qual é possível detectar várias solicitações de token que usam o mesmo token a fim de descartá-las. Quanto este recurso está habilitado, a detecção de repetição de token protege a integridade das solicitações de autenticação tanto no perfil passivo do WS-Federation quanto no perfil de SAML WebSSO, certificando-se de que o mesmo token nunca é usado mais de uma vez.
  
Esse recurso deve ser habilitado em situações em que há grandes preocupações com a segurança, como quando se usa quiosques. Para obter mais informações sobre a detecção de repetição de token, consulte [práticas recomendadas para o planejamento seguro e a implantação do AD FS 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Acesso de usuários externos

A configuração de um proxy ADFS ou de proxy reverso para dar suporte à autenticação de dois fatores do Skype for Business a partir de redes externas não é abordada nestes tópicos.
  
## <a name="see-also"></a>Confira também

[Configurar a autenticação de dois fatores no Skype for Business Server](configure-two-factor.md)
  
