---
title: Configurar as políticas de inicialização do cliente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Resumo: Como gerenciar políticas de grupo.'
ms.openlocfilehash: 5d5a2d3a7939f34bb42995bb69280fb7891736ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805981"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurar as políticas de inicialização do cliente
 
**Resumo:** Como gerenciar políticas de grupo.
  
O Console de Gerenciamento de Política de Grupo (GPMC) e o Editor de Objeto de Política de Grupo são ferramentas que você usa para gerenciar a Política de Grupo. Incluídos no Modelo Administrativo da Política de Grupo do Office estão os Modelos Administrativos lync16.admx (ADMX) e .adml (ADML), que contêm as configurações de política baseadas no Registro para o Skype for Business que você configura para objetos de Política de Grupo no domínio. Os arquivos ADML são complementos específicos do idioma para arquivos ADMX. Cada arquivo ADMX e ADML contém as configurações de política para um único aplicativo do Office. Você pode baixar os arquivos do Modelo Administrativo do [Office 2016 (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) gratuitamente no Centro de Download da Microsoft.
  
Para clientes do Skype for Business, há várias políticas de inicialização de cliente que você deve considerar configurar antes que os usuários se inscrevam no servidor pela primeira vez. Por exemplo, os servidores padrão e o modo de segurança que o cliente deve usar até que a entrada seja concluída. Você pode usar a Política de Grupo para estabelecer essas configurações nos registros do computador dos usuários antes que eles se inscrevam e comecem a receber configurações de provisionamento em banda do servidor. A tabela a seguir lista as configurações de Política de Grupo disponíveis para o Skype for Business.
  
**Configurações de Política de Grupo para o Skype for Business**

|Configuração da Política de grupo|Descrição|
|:-----|:-----|
|Especificar Servidor (ConfigurationMode)  <br/> | Especifica como o Skype for Business identifica o transporte e o servidor a ser usado durante a conexão. Dentro dessa configuração, especifique o seguinte: <br/>  ServerAddressExternal: especifica o nome do servidor ou endereço IP usado por clientes e contatos federados ao se conectar de fora do firewall externo. <br/>  ServerAddressInternal: especifica o nome do servidor ou endereço IP usado quando os clientes se conectam de dentro do firewall da organização. <br/>  Transporte: Especifica o Protocolo de Controle de Transmissão (TCP) ou o Protocolo de Camada de Transporte (TLS). <br/> |
|Versões adicionais do servidor com suporte (ConfiguredServerCheckValues)  <br/> |Especifica uma lista de nomes de versão de servidor separados por pontos-e-vírgulas que o Skype for Business Server fará logoff, além das versões de servidor que são suportadas por padrão.  <br/> |
|Desabilitar o carregamento automático de logs de falha de login (DisableAutomaticSendTracing)  <br/> |Carrega automaticamente os logs de falha de login no Skype for Business Server para análise. Nenhum registro será carregado automaticamente se a conexão for bem-sucedida. Se essa política não estiver configurada, ocorrerá o seguinte:  <br/> Para usuários do Skype for Business Online: os logs de falha de logor são carregados automaticamente. Para usuários locais do Skype for Business: uma caixa de diálogo de confirmação é mostrada para o usuário antes do carregamento. Quando essa configuração é desabilitada, os logs de login são carregados automaticamente no Skype for Business Server para usuários do Skype for Business local e do Skype for Business Online. Quando essa configuração está habilitada, os logs de login nunca são carregados automaticamente.  <br/> |
|Desabilitar fallback HTTP para conexão SIP (DisableHttpConnect)  <br/> |Impede que o Skype for Business Server tentar se conectar ao servidor usando HTTP, se TLS ou TCP não estão disponíveis. Por padrão, o Skype for Business tenta primeiro se conectar ao servidor usando TLS ou TCP e, se nenhum desses métodos de transporte for bem-sucedido, o Skype for Business tentará se conectar usando HTTP. Use essa política para desabilitar a tentativa de conexão HTTP de fallback.  <br/> |
|Exigir credenciais de logon (DisableNTCredentials)  <br/> |Exige que o usuário forneça credenciais de logon para o Skype for Business em vez de usar automaticamente credenciais do Windows durante a conexão com um servidor SIP.  <br/> |
|Desabilitar a verificação de versão do servidor (DisableServerCheck)  <br/> |Se você definir essa política como 1, impedirá o Skype for Business de verificar o nome e a versão do servidor antes de entrar. Por padrão, o Skype for Business faz essas verificações antes de entrar.  <br/> |
|Habilitar o uso do BITS para baixar arquivos do Serviço de Agendamento de Endereços (EnableBitsForGalDownload)  <br/> |Permite que o Skype for Business use BITS (Serviço de Transferência Inteligente em Segundo Plano) para baixar os arquivos dos Serviços de Agenda.  <br/> |
|Configurar o modo de segurança SIP (EnableSIPHighSecurityMode)  <br/> |Permite que o Skype for Business envie e receba mensagens instantâneas com mais segurança. Essa política não tem efeito sobre os serviços .NET ou Microsoft Exchange Server do Windows.  <br/> Se você não definir essa configuração de política, o Skype for Business poderá usar qualquer transporte. Mas se ele não usar TLS e se o servidor autenticar usuários, o Skype for Business deverá usar a autenticação NTLM ou Kerberos.  <br/> |
|Atraso inicial do download do livro de endereço global (GalDownloadInitialDelay)  <br/> |Especifica o período antes de um download da GAL (lista de endereços global) ocorrer. O valor padrão é 60 minutos, o que significa que o servidor atrasa o download do arquivo GAL por um período aleatório entre 0 e 60 minutos.  <br/> |
|Impedir que os usuários executam o Skype for Business (PreventRun)  <br/> |Impede que os usuários executam o Skype for Business. Você pode configurar essa definição de diretiva em Configuração do Computador e em Configuração do Usuário, mas a definição de Configuração do Computador tem precedência.  <br/> |
|Permitir o armazenamento de senhas de usuário (SavePassword)  <br/> |Permite que o Skype for Business armazene senhas.  <br/> |
|Configurar o modo de compactação SIP (SipCompression)  <br/> |Especifica quando ativar a compactação SIP. Por padrão, a compactação SIP é habilitada com base na velocidade do adaptador. Observe que a configuração dessa política pode causar um aumento no tempo de login.  <br/> |
|Lista de Domínios Confiáveis (TrustModelData)  <br/> |Lista os domínios confiáveis que não corresponderem ao prefixo do domínio SIP do cliente.  <br/> |
   
As políticas configuradas no servidor têm precedência sobre as configurações de Política de Grupo e as opções de cliente configuradas pelo usuário. A tabela a seguir resume a ordem na qual as configurações têm precedência quando ocorre um conflito.
  
**Precedência das Políticas de Grupo**

|**Precedence**|**Local ou método da configuração**|
|:-----|:-----|
|1   <br/> |Provisionamento em banda do Skype for Business Server  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |A caixa de diálogo Opções no Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Para definir configurações de Política de Grupo usando os arquivos de modelo administrativo do Skype for Business

1. Crie uma pasta de nível raiz para conter todos os arquivos ADMX com neutralidade de idioma. Por exemplo, crie a pasta raiz do repositório central em seu controlador de domínio neste local:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Este procedimento assume que você deseja gerenciar vários computadores em seu domínio. Nesse caso, você armazena os modelos em um armazenamento central na pasta Sysvol no controlador de domínio primário. Isso oferece um local de repositório central para Modelos Administrativos do domínio. 
  
2. Crie uma subpasta para cada idioma que você usará. Essas subpastas conterão os arquivos de recurso ADML específicos do idioma. Por exemplo, crie uma subpasta para o Inglês dos Estados Unidos (EN-US) neste local:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

