---
title: Skype para solução de problemas para erros de entrada no Business Online para administradores
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Saiba as causas comuns para Skype para erros de entrada Business Online e trabalho por meio de solucionar esses problemas. '
ms.openlocfilehash: 560b8244cae99d0af2603181d3cf0c2a02c491d5
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501240"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Skype para solução de problemas para erros de entrada no Business Online para administradores

Para solucionar Skype para erros de entrada no Business Online, inicie, eliminando as causas mais comuns de dificuldade entrar. Se necessário, você poderá seguir etapas com base no tipo de erro de resolução específica. Se o usuário ainda não conseguir entrar, coletar informações adicionais e, em seguida, seek ajuda adicional. 
  
## <a name="what-do-you-want-to-do"></a>O que você deseja fazer?
<a name="top"> </a>

> [Procurar causas comuns da Skype para erros de entrada no Business Online](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
    
> [Siga as etapas de solução para um erro específico (Enterprise)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
    
> [Adicionar uma entrada de firewall para msoidsvc.exe ao seu servidor proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
    
> [Atualizar configurações de DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
    
> [Instalar um certificado SSL de terceiros em seu servidor ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
    
> [Atualizar as credenciais de segurança](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
    
> [Modifique as chaves de registro de TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
    
> [Atualizar configurações de usuário no Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
    
> [Use a guia resolução de problemas do Microsoft Support](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
    
> [Coletar mais informações e buscar ajuda adicional](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)
    
## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Procurar causas comuns da Skype para erros de entrada no Business Online
<a name="toc323194094"> </a>

A maioria dos problemas de login podem ser rastreados para um pequeno número de causas e muitos deles são fáceis de corrigir. A tabela a seguir lista algumas causas comuns de erros de entrada e algumas etapas que você ou os usuários podem ser executadas para resolvê-los.
  
|**Possível causa**|**Resolução**|
|:-----|:-----|
|Durante a entrada, uma caixa de diálogo é exibida que contenha a frase a seguir: **não foi possível verificar se o servidor é confiável para o seu endereço de entrada. Conectar mesmo assim?** <br/> |Verifique se o nome de domínio na caixa de diálogo é um servidor confiável na sua organização — por exemplo, **domainName.contoso.com**. Peça que o usuário para selecionar a caixa de seleção **Sempre confiar neste servidor** e clique em **Conectar**. <br/> Os clientes corporativos podem impedir que essa mensagem apareça quando um usuário entrar pela primeira vez, modificando o registro do Windows no computador de cada usuário. Para obter detalhes, consulte [chaves do registro para modificar TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
|Endereço de entrada erros de digitação, nome de usuário ou senha  <br/> | Confirme que o nome de usuário e a senha do usuário estão corretas. <br/>  Verificar se o nome de entrada do usuário é formatado como se segue: **bobk@contoso.com**. Isso pode ser diferente do que o formato usado para entrar rede da sua organização.  <br/>  Peça que o usuário tentar entrar novamente. <br/> |
|Recuperação de senha  <br/> |Redefinir a senha do usuário e notificá-lo sobre a nova senha temporária.  <br/> |
|Não licenciada para usar o Skype para negócios Online  <br/> |Confirme que o usuário está registrado como um Skype para usuário Business Online. Caso contrário, registre o usuário e, em seguida, solicite que ela entrar novamente.  <br/> |
|Versão incorreta do Skype para Business Online instalado  <br/> |Esse problema é geralmente associado a uma mensagem de erro que contenha a frase a seguir: **o serviço de autenticação pode ser incompatível com esta versão do programa**.  <br/> Peça que o usuário desinstalar e reinstalar o Skype para negócios Online do Portal do Office 365.  <br/> |
|Problema adquirir um certificado pessoal é necessária para entrar  <br/> |Se o endereço de entrada do usuário foi alterada recentemente, eles talvez seja necessário excluir dados armazenados em cache entrar. Peça aos usuários para sair, clique no botão Excluir link na tela entrar minhas informações de entrada e tente novamente.  <br/> |
|Configurar um nome de domínio personalizado e as alterações podem não ter terminado propagando através do sistema.  <br/> |Em primeiro lugar, certifique-se de que você modificou os registros de serviço de nome de domínio (DNS) para refletir a alteração.  <br/> Se você já tiver feito as alterações necessárias do DNS, avisa o usuário tentar fazer logon no posteriormente. Alterações DNS podem levar até 72 horas sejam refletidas em todo o sistema.  <br/> |
|Sistema relógio fora de sincronia com o relógio do servidor  <br/> |Certifique-se de que seu controlador de domínio de rede está sincronizando com uma fonte de tempo externa confiável. Para obter detalhes, consulte o artigo da Base de Conhecimento Microsoft 816042, [como configurar um servidor de horário autoritativo no Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/> |
   
Para solucionar Skype para erros de entrada no Business Online, inicie, eliminando as causas mais comuns de dificuldade entrar. Se necessário, você poderá seguir etapas com base no tipo de erro de resolução específica. Se o usuário ainda não conseguir entrar, coletar informações adicionais e, em seguida, seek ajuda adicional. 
  
## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Siga as etapas de solução para um erro específico (Enterprise)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Estas instruções destinam-se principalmente para clientes do Microsoft Office 365 planejar F. Se você for um cliente do Office 365 planejar P, continue a seção a seguir,[coletar mais informações e buscar ajuda adicional ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information). 
  
Se o usuário não conseguir entrar após ter tentado as sugestões da seção anterior, você poderá fazer adicionais de solução de problemas com base no tipo de erro. A tabela abaixo lista as mensagens de erro mais comuns e as possíveis causas. A tabela a seguir está os procedimentos detalhados para cada questão de endereços.
  
|**Mensagem de erro**|**Possível causa**|**Resolução**|
|:-----|:-----|:-----|
|Endereço de entrada não encontrado  <br/> |As solicitações de entrada da Microsoft Online Services Sign-On Assistant (msoidsvc.exe) não serão através de seu firewall externo ou o servidor proxy.  <br/> |[Adicionar uma entrada de firewall para msoidsvc.exe ao seu servidor proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|Servidor está temporariamente indisponível  <br/> |Se sua organização tiver um domínio personalizado, as configurações necessárias do sistema de nome de domínio (DNS) podem ser ausentes ou incorretos.  <br/> |[Atualizar configurações de DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|Servidor está temporariamente indisponível  <br/> |Se sua organização estiver usando o logon único com o Active Directory Federation Services (ADFS), você pode ter usado um certificado autoassinado de camada de soquete seguro (SSL) em vez de um em uma autoridade de certificação de terceiros.  <br/> |[Instalar um certificado SSL de terceiros em seu servidor ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Problema adquirir um certificado pessoal é necessária para entrar  <br/> |Se você já tiver removido os dados armazenados em cache do servidor usado para entrar na e o erro continua a ser exibida, credenciais de segurança do usuário podem estar corrompidas ou uma pasta RSA no computador do usuário pode estar bloqueando autenticação.  <br/> |[Atualizar as credenciais de segurança](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Uma caixa de diálogo de confiança do certificado aparece quando um usuário entrar pela primeira vez.  <br/> |Esta caixa de diálogo é exibida se seu Skype para Business server ainda não estiver listado na chave do registro **TrustModelData** . <br/> |[Modifique as chaves de registro de TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|O usuário não é habilitados para SIP  <br/> |Se sua organização tiver uma instalação anterior do Microsoft Office Communications Server ou Microsoft Lync Server 2010, você pode não ter excluído os usuários do servidor antes de encerrar a ele. Como resultado, o atributo **msRTCSIP-UserEnabled** ainda é definido como **FALSE** nos serviços de domínio Active Directory. <br/> |[Atualizar configurações de usuário no Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |
   
### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Adicionar uma entrada de firewall para msoidsvc.exe ao seu servidor proxy
<a name="add-a-firewall"> </a>

Esse procedimento é uma correção possível para a seguinte mensagem de erro: **endereço de entrada não encontrado**.

> [!NOTE]
> As etapas a seguir consideram que você está usando o Microsoft Forefront Threat Management Gateway (TMG) 2010. Se você tiver uma solução de gateway web diferente, use as configurações descritas na etapa 4 abaixo.
  
  
Para criar uma entrada de aplicativo para Msoidsvc.exe no Forefront TMG 2010, siga estas etapas:
  
1. No painel à esquerda do Forefront, clique em **rede**.
    
2. Clique na guia **rede** . Sob a guia **tarefas** no painel direito, clique em **Configurar definições de cliente do Forefront TMG**.
    
3. Na caixa de diálogo **Configurações de cliente do Forefront TMG** , clique em **novo**.
    
4. Na caixa de diálogo **Configuração de entrada de aplicativo** , configure as regras a seguir:
    
|**Aplicativo**|**Chave**|**Valor**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Desabilitar  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
Para obter detalhes, consulte o artigo da Base de Conhecimento Microsoft 2409256, [que você não pode se conectar ao Skype para Business Online porque um firewall local bloqueia a conexão](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).
  
### <a name="update-dns-settings"></a>Atualizar configurações de DNS
<a name="update-dns-service"> </a>

Se sua organização tiver um domínio personalizado, esse procedimento é uma correção possível para a seguinte mensagem de erro: **servidor está temporariamente indisponível**.
  
- Para obter informações sobre como adicionar o seguinte registro CNAME para o seu domínio, entre em contato com seu registrador de nome de domínio:
    
  - **Tipo de registro de DNS**: CNAME 
    
  - **Nome**: sip
    
  - **Valor/destino**: sipdir.online.microsoft.com
    
Para obter detalhes, consulte o artigo da Base de Conhecimento Microsoft 2566790, [Skype de solução de problemas para problemas de configuração de DNS de negócios Online no Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).
  
### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Instalar um certificado SSL de terceiros em seu servidor ADFS
<a name="verify-upn-and"> </a>

Para instalar um certificado SSL de terceiros em seu servidor de serviços de federação de domínio Active (ADFS), siga estas etapas:
  
1. Obter um certificado SSL de uma autoridade de certificação de terceiros, como VeriSign ou Thawte.
    
2. Instale o certificado do seu servidor ADFS usando o console de gerenciamento do ADFS. 
    
### <a name="update-security-credentials"></a>Atualizar as credenciais de segurança
<a name="update-security-credentials"> </a>

Esse procedimento é uma correção possível para a mensagem de erro **problema adquirir um certificado pessoal precisa para entrar**.
  
Para eliminar possíveis problemas de certificado ou credential, primeiro renove o certificado do usuário no Gerenciador de certificados do Windows. Para fazer isso, siga estas etapas:
  
1. Abra o Gerenciador de certificados do Windows. Para fazer isso, clique em **Iniciar**, clique em **Executar**, digite **certmgr. msc**e clique em **Okey**. 
    
2. Clique duas vezes em **pessoal**e, em seguida, clique duas vezes em **certificados**. 
    
3. Classificar por coluna **Emitido por** e, em seguida, procure por um certificado emitido pelo Communications Server.
    
4. Com o botão direito no certificado e, em seguida, clique em **Excluir**. 
    
Em seguida, se o usuário estiver executando o Windows 7, remova suas credenciais armazenadas no Gerenciador de credenciais do Windows. Para fazer isso, siga estas etapas:
  
1. Clique em **Iniciar**, clique em **Painel de controle**e, em seguida, clique em **Gerenciador de credenciais**. 
    
2. Localize o conjunto de credenciais que é usado para conectar Skype para Business Online. 
    
3. Expanda o conjunto de credenciais e, em seguida, clique em **Remover do Vault**. 
    
4. Entrar novamente e reinserir as credenciais do usuário.
    
Finalmente, se o usuário ainda não conseguir entrar depois que você atualizou suas credenciais, tente excluir a pasta RSA no computador do usuário, pois ele pode estar bloqueando a conclusão do processo de autenticação de usuário:
  
1. Entrar no computador do usuário usando uma conta de administrador.
    
2. Se necessário, ative a opção de exibição da pasta **Mostrar arquivos ocultos**. 
    
3. Digite o seguinte na barra de endereços do arquivo Explorer: **c:\\Documents and Settings\\UserName\\dados do aplicativo\\Microsoft\\criptografia\\RSA**, onde o ***nome de usuário*** é o seu nome de logon do Windows.
    
4. Exclua qualquer pasta que começa com o nome **S-1-5-21 -** seguido por uma cadeia de caracteres de números.
    
### <a name="modify-trustmodeldata-registry-keys"></a>Modifique as chaves de registro de TrustModelData
<a name="modify-trustmodeldata-registry"> </a>

Quando um usuário entrar pela primeira vez, eles podem receber uma caixa de diálogo que contém parecido com o seguinte: **não foi possível verificar se o servidor é confiável para o seu endereço de entrada. Conectar mesmo assim?** Esse é um recurso de segurança e não um erro. No entanto, você pode impedir que a caixa de diálogo que aparecem, usando um objeto de diretiva de grupo (GPO) para atualizar máquinas dos usuários com seu nome de domínio antes de eles entrarem pela primeira vez. Para realizar isso, faça o seguinte:
  
- Criar e implantar um GPO que acrescenta sua Skype para nome de domínio de negócios — por exemplo, domainName.contoso.com—to o valor atual do HKEY_LOCAL_MACHINE\\Software\\políticas\\Microsoft\\Communicator\\ TrustModelData.
    
> [!IMPORTANT]
>  Você deve *Acrescentar* o nome do seu domínio ao valor existente, não basta substituí-la.
  
Para obter detalhes, consulte o artigo da Base de Conhecimento Microsoft 2531068, [que Skype para negócios (Lync) não foi possível verificar se o servidor é confiável para o seu endereço de entrada](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).
  
### <a name="update-user-settings-in-active-directory"></a>Atualizar as configurações de usuário no Active Directory
<a name="update-user-settings"> </a>

Se sua organização tiver uma instalação anterior do Microsoft Office Communications Server ou Microsoft Lync Server 2010, você pode não ter excluído os usuários do servidor antes de encerrar a ele. Como resultado, o atributo **msRTCSIP-UserEnabled** ainda é definido como **FALSE** nos serviços de domínio Active Directory.
  
Para corrigir esse problema, siga estas etapas:
  
1. Atualize o atributo **msRTCSIP-UserEnabled** para todos os usuários afetados como **TRUE**.
    
2. Execute novamente a ferramenta de sincronização de diretório do Microsoft Online Services (DirSync). Para obter detalhes, consulte [diretórios AIntegrate seu local com o Windows Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx). 
    
Para solucionar Skype para erros de entrada no Business Online, inicie, eliminando as causas mais comuns de dificuldade entrar. Se necessário, você poderá seguir etapas com base no tipo de erro de resolução específica. Se o usuário ainda não conseguir entrar, coletar informações adicionais e, em seguida, seek ajuda adicional. 
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Use a guia resolução de problemas do Microsoft Support
<a name="toc325626447"> </a>

Se você ainda não foi possível resolver problemas de entrada do usuário, revise as sugestões no artigo da Base de Conhecimento Microsoft 2541980, [como solucionar problemas de login no Skype para negócios Online](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).
  
## <a name="collect-more-information-and-seek-additional-help"></a>Coletar mais informações e buscar ajuda adicional
<a name="collect-more-information"> </a>

Se você ter seguido as diretrizes acima e ainda não é possível resolver problemas de login, você deve coletar informações adicionais e entre em contato com o suporte técnico. Para fazer isso, siga estas etapas: 
  
1. Obter os arquivos de log e os detalhes do log de eventos do Windows no computador do usuário. Para obter instruções detalhadas, consulte o tópico de Ajuda do usuário final [ativem logs de erros no Lync](http://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).
    
2. Envie os arquivos de log e as informações detalhadas sobre o erro para suporte técnico da Microsoft.
    
Você pode ser solicitado a fornecer informações de diagnósticos adicionais por meio da instalação do Microsoft Online Services diagnóstico e o Kit de ferramentas de suporte de Logging (MOSDAL) na máquina do usuário afetado. Para obter detalhes, consulte [usando as ferramentas de suporte do MOSDAL](http://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).
  
Para solucionar Skype para erros de entrada no Business Online, inicie, eliminando as causas mais comuns de dificuldade entrar. Se necessário, você poderá seguir etapas com base no tipo de erro de resolução específica. Se o usuário ainda não conseguir entrar, coletar informações adicionais e, em seguida, seek ajuda adicional. 
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 