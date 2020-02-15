---
title: Configurar as políticas de inicialização do cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Resumo: como gerenciar políticas de grupo.'
ms.openlocfilehash: 4db9becc32e8f9bca99f06ac4533d33e82666591
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029052"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurar as políticas de inicialização do cliente
 
**Resumo:** Como gerenciar políticas de grupo.
  
O GPMC (console de gerenciamento de política de grupo) e o editor de objeto de diretiva de grupo são ferramentas que você usa para gerenciar a política de grupo. Incluído no modelo administrativo da política de grupo do Office estão os modelos administrativos do lync16. admx (ADMX) e. adml (ADML), que contêm as configurações de política com base no registro para o Skype for Business que você configura para objetos de política de grupo no domínio. Os arquivos ADML são complementos específicos do idioma para arquivos ADMX. Cada arquivo ADMX e ADML contém as configurações de política para um único aplicativo do Office. Você pode [baixar os arquivos de modelo administrativo do Office 2016 (admx/adml)](https://www.microsoft.com/download/details.aspx?id=49030) gratuitamente no centro de download da Microsoft.
  
Para clientes do Skype for Business, há várias políticas de inicialização do cliente que devem ser consideradas configuradas antes que os usuários entrem no servidor pela primeira vez. Por exemplo, os servidores e o modo de segurança padrão que o cliente deve usar até que o logon seja concluído. Você pode usar a política de grupo para estabelecer essas configurações nos registros de computador dos usuários antes de entrar e começar a receber as configurações de provisionamento em banda no servidor. A tabela a seguir lista as configurações de política de grupo disponíveis para o Skype for Business.
  
**Configurações de política de grupo para o Skype for Business**

|Configuração da Política de grupo|Descrição|
|:-----|:-----|
|Especificar servidor (ConfigurationMode)  <br/> | Especifica como o Skype for Business identifica o transporte e o servidor a serem usados durante a entrada. Nesta configuração, especifique o seguinte: <br/>  ServerAddressExternal: especifica o nome do servidor ou endereço IP usado por clientes e contatos federados ao se conectar de fora do firewall externo. <br/>  ServerAddressInternal: especifica o nome do servidor ou endereço IP usado quando os clientes se conectam de dentro do firewall da organização. <br/>  Transport: especifica o protocolo de controle de transmissão (TCP) ou TLS (Transport Layer Security). <br/> |
|Versões de servidor adicionais suportadas (ConfiguredServerCheckValues)  <br/> |Especifica uma lista de nomes de versão do servidor separados por ponto e vírgula nos quais o Skype for Business Server fará logon, além das versões de servidor que são suportadas por padrão.  <br/> |
|Desabilitar o carregamento automático de logs de falha de entrada (DisableAutomaticSendTracing)  <br/> |Carrega automaticamente os logs de falha de entrada no Skype for Business Server para análise. Nenhum log será carregado automaticamente se a conexão for bem-sucedida. Se essa política não estiver configurada, ocorrerá o seguinte:  <br/> Para usuários do Skype for Business Online: os logs de falha de entrada são carregados automaticamente. Para usuários locais do Skype for Business: uma caixa de diálogo de confirmação é exibida para o usuário antes do carregamento. Quando essa configuração é desabilitada, os logs de entrada são carregados automaticamente para o Skype for Business Server para usuários do Skype for Business no local e no Skype for Business online. Quando essa configuração é habilitada, os logs de entrada nunca são carregados automaticamente.  <br/> |
|Desabilitar fallback de HTTP para conexão SIP (DisableHttpConnect)  <br/> |Impede que o Skype for Business Server tente se conectar ao servidor usando HTTP, se TLS ou TCP não estiverem disponíveis. Por padrão, o Skype for Business primeiro tenta se conectar ao servidor usando TLS ou TCP e, se nenhum desses métodos de transporte for bem-sucedido, o Skype for Business tentará se conectar usando HTTP. Use essa política para desabilitar a tentativa de conexão HTTP de fallback.  <br/> |
|Exigir credenciais de logon (DisableNTCredentials)  <br/> |Requer que o usuário forneça credenciais de logon para o Skype for Business em vez de usar automaticamente as credenciais do Windows durante a entrada em um servidor SIP.  <br/> |
|Desabilitar a verificação de versão do servidor (DisableServerCheck)  <br/> |Se você definir esta política como 1, impede que o Skype for Business Verifique o nome do servidor e a versão antes de entrar. Por padrão, o Skype for Business faz essas verificações antes de entrar.  <br/> |
|Habilitar o uso de BITS para baixar arquivos de serviço de catálogo de endereços (EnableBitsForGalDownload)  <br/> |Permite que o Skype for Business use o serviço de transferência inteligente em segundo plano (BITS) para baixar os arquivos dos serviços de catálogo de endereços.  <br/> |
|Configurar o modo de segurança SIP (EnableSIPHighSecurityMode)  <br/> |Permite que o Skype for Business envie e receba mensagens instantâneas com mais segurança. Essa política não tem efeito sobre os serviços .NET ou Microsoft Exchange Server do Windows.  <br/> Se você não definir essa configuração de política, o Skype for Business poderá usar qualquer transporte. Mas se ele não usar TLS e se o servidor autenticar usuários, o Skype for Business deverá usar a autenticação NTLM ou Kerberos.  <br/> |
|Atraso inicial de download do catálogo de endereços global (GalDownloadInitialDelay)  <br/> |Especifica o período de tempo antes da ocorrência de um download da GAL (lista de endereços global). O valor padrão é 60 minutos, o que significa que o servidor atrasa o download do arquivo GAL por um período aleatório entre 0 e 60 minutos.  <br/> |
|Impedir que os usuários executem o Skype for Business (PreventRun)  <br/> |Impede que os usuários executem o Skype for Business. Você pode configurar essa definição de diretiva em Configuração do Computador e em Configuração do Usuário, mas a definição de Configuração do Computador tem precedência.  <br/> |
|Permitir o armazenamento de senhas de usuário (SavePassword)  <br/> |Permite que o Skype for Business armazene senhas.  <br/> |
|Configurar o modo de compactação SIP (SipCompression)  <br/> |Especifica quando ativar a compactação SIP. Por padrão, a compactação SIP é ativada com base na velocidade do adaptador. Observe que a configuração dessa política pode causar um aumento no tempo de login.  <br/> |
|Lista de domínios confiáveis (TrustModelData)  <br/> |Lista os domínios confiáveis que não correspondem ao prefixo do domínio SIP do cliente.  <br/> |
   
As políticas configuradas no servidor têm precedência sobre as configurações de Política de Grupo e as opções de cliente configuradas pelo usuário. A tabela a seguir resume a ordem na qual as configurações têm precedência quando ocorre um conflito.
  
**Precedência das Políticas de Grupo**

|**Precedence**|**Local ou método da configuração**|
|:-----|:-----|
|1   <br/> |Provisionamento em banda do Skype for Business Server  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |A caixa de diálogo opções no Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Para definir as configurações de diretiva de grupo usando os arquivos de modelo administrativo do Skype for Business

1. Crie uma pasta de nível de raiz para que contenha todos os arquivos ADMX de idioma neutro. Por exemplo, crie a pasta raiz do repositório central em seu controlador de domínio neste local:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Este procedimento pressupõe que você deseja gerenciar vários computadores em seu domínio. Nesse caso, você armazena os modelos em um repositório central na pasta SYSVOL no controlador de domínio primário. Isso oferece um local de repositório central para Modelos Administrativos do domínio. 
  
2. Crie uma subpasta para cada idioma que você usará. Essas subpastas conterão os arquivos de recurso ADML específicos do idioma. Por exemplo, crie uma subpasta para o inglês dos Estados Unidos (EN-US) neste local:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

