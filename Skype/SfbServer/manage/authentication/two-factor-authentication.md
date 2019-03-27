---
title: Gerenciar a autenticação de dois fatores no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumo: Gerencie autenticação de dois fatores no Skype para Business Server.'
ms.openlocfilehash: ce6d43b8ace741a754cb4406235534fd83e414b3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888399"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Gerenciar a autenticação de dois fatores no Skype para Business Server
 
**Resumo:** Gerencie a autenticação de dois fatores no Skype para Business Server.
  
A autenticação de dois fatores oferece maior segurança ao exigir que os usuários forneçam duas formas de autenticação ou identificação, ou seja, uma combinação de nome de usuário/senha e um token ou certificado. Isso também é conhecida como "algo que você tem, algo que você conhece." 
  
Um exemplo típico da autenticação de dois fatores com um certificado é o uso de cartões inteligentes. Um cartão inteligente contém um certificado associado à conta do usuário e pode ser validado com as informações e certificado e usuário que estão armazenadas em um servidor. Ao comparar as informações do usuário (nome do usuário e senha) ao certificado fornecido, o servidor valida as credenciais e autentica o usuário.
  
Ao configurar um Skype para ambiente de servidor de negócios para suportar a autenticação de dois fatores, considere os seguintes assuntos.
  
## <a name="client-support"></a>Suporte de Cliente

As atualizações cumulativas do Lync Server 2013: julho de 2013 cliente de desktop e do Skype para o cliente de negócios são os únicos clientes que oferecem suporte a autenticação de dois fatores no momento.
  
## <a name="topology-requirements"></a>Requisitos de topologia

Os clientes são altamente encorajados implantar a autenticação de dois fatores usando Skype dedicado para Business Server com borda, diretor e Pools de usuário. Para habilitar a autenticação passiva para usuários, é necessário desabilitar outros métodos de autenticação para outras funções e serviços, tais como:
  
|**Tipo de configuração**|**Tipo de serviço**|**Função de servidor**|**Tipo de autenticação a ser desabilitada**|
|:-----|:-----|:-----|:-----|
|Serviço Web  <br/> |WebServer  <br/> |Diretor  <br/> |Kerberos, NTLM e Certificado  <br/> |
|Serviço Web  <br/> |WebServer  <br/> |Front-End  <br/> |Kerberos, NTLM e Certificado  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Borda  <br/> |Kerberos e NTLM  <br/> |
|Proxy  <br/> |Registrador  <br/> |Front-End  <br/> |Kerberos e NTLM  <br/> |
   
A não ser que esses tipos de autenticação estejam desabilitados no nível de serviço, todas as outras versões do cliente não conseguirão se conectar enquanto a autenticação de dois fatores estiver habilitada em sua implantação.
  
## <a name="skype-for-business-service-discovery"></a>Descoberta de Serviços do Skype for Business

Registros DNS usados pelos clientes internos e/ou externos para descobrir Skype para serviços corporativos de devem ser configurados para ser resolvido para um Skype para Business server não está habilitado para a autenticação de dois fatores. Com essa configuração, os usuários do Skype para os Pools de negócios que não estão habilitados para autenticação de dois fatores não precisará inserir um PIN para autenticar, enquanto os usuários do Skype para Pools de negócios que estão habilitados para autenticação de dois fatores serão precisarão para inserir o PIN para autenticar.
  
## <a name="exchange-authentication"></a>Autenticação do Exchange

Clientes que implantaram autenticação de dois fatores para o Microsoft Exchange podem achar que certos recursos no cliente não estão disponíveis. Isso é atualmente por design, pois o Skype para o cliente de negócios não dá suporte a autenticação de dois fatores para recursos que dependem de integração do Exchange.
  
## <a name="contacts"></a>Contatos

Skype para usuários de negócios que estiverem configurados para aproveitar o recurso de repositório unificado de contatos encontrará que seus contatos não estão mais disponíveis após entrar com autenticação de dois fatores.
  
Você deve usar o cmdlet **Invoke-CsUcsRollback** remover contatos do usuário existente do repositório unificado de contatos e armazená-los no Skype para Business Server antes de habilitar a autenticação de dois fatores.
  
## <a name="skill-search"></a>Pesquisa de Habilidades

Os clientes que configuraram o recurso de pesquisa de habilidade em seu Skype para ambiente de negócios encontrará que esse recurso não funciona quando Skype para a empresa está habilitado para a autenticação de dois fatores. Isso ocorre devido ao projeto, já que o Microsoft SharePoint não é compatível com a autenticação de dois fatores.
  
## <a name="credentials"></a>Credenciais

Há várias considerações de implantação envolvendo salva Skype para credenciais de negócios que pode afetar os usuários configurados para usar a autenticação de dois fatores.
  
### <a name="deleting-saved-credentials"></a>Exclusão de Credenciais Salvas

Usuários devem usar a opção **Excluir minhas informações de entrar** no Skype para o cliente de negócios e excluir sua pasta de perfil SIP de %localappdata%\Microsoft\Office\15.0\Skype for Business antes de tentar entrar pela primeira vez usando dois fatores autenticação.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Com o método de autenticação Kerberos ou NTLM, as credenciais do Windows do usuário são usadas automaticamente para autenticação. Em um Skype típica para implantação Business Server onde o Kerberos e/ou NTLM está habilitado para autenticação, os usuários não devem ter que inserir suas credenciais cada vez que entrarem.
  
Se as credenciais dos usuários forem inadvertidamente solicitadas antes de ser necessário informar o PIN, a chave de registro **DisableNTCredentials** pode estar configurada por engano nos computadores clientes, possivelmente através de uma Política de Grupo.
  
Para impedir que a solicitação adicional de credenciais, crie a seguinte entrada de registro na estação de trabalho local ou usar o Skype para o modelo administrativo de negócios para aplicar a todos os usuários de um determinado pool usando a diretiva de grupo:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Quando um usuário entra no Skype para negócios pela primeira vez, o usuário é solicitado a salvar sua senha. Se selecionada, esta opção permite que o certificado de cliente do usuário a serem armazenados no repositório de certificados pessoais e credenciais do Windows do usuário a serem armazenados no Gerenciador de credencial do computador local.
  
A configuração de registro **SavePassword** deve ser desabilitada quando Skype para negócios é configurado para oferecer suporte à autenticação de dois fatores. Para impedir usuários de salvar suas senhas, altere a seguinte entrada do registro na estação de trabalho local ou use o Skype para o modelo administrativo de negócios para aplicar a todos os usuários para um determinado pool usando a diretiva de grupo:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 Token Replay

O AD FS 2.0 oferece um recurso chamado detecção de repetição de token, pelo qual é possível detectar várias solicitações de token que usam o mesmo token a fim de descartá-las. Quanto este recurso está habilitado, a detecção de repetição de token protege a integridade das solicitações de autenticação tanto no perfil passivo do WS-Federation quanto no perfil de SAML WebSSO, certificando-se de que o mesmo token nunca é usado mais de uma vez.
  
Esse recurso deve ser habilitado em situações em que há grandes preocupações com a segurança, como quando se usa quiosques. Para obter mais informações sobre detecção de reprodução de token, consulte [Práticas recomendadas para proteger o planejamento e implantação do AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Acesso de usuários externos

Configurando um Proxy do ADFS ou Proxy reverso para suportar Skype para autenticação de dois fatores comerciais de redes externas não é abordada nestes tópicos.
  
## <a name="see-also"></a>Consulte Também

[Configurar a autenticação de dois fatores no Skype para Business Server](configure-two-factor.md)
  
