---
title: Solucionando erros de entrada no Skype for Business Online para administradores
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Aprenda causas comuns para erros de sinal do Skype for Business Online e trabalhe na solução de problemas. '
ms.openlocfilehash: 1fdb764f9557e9c5b759b50cadf2650a6af75dc1dc262ff45648360807436881
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303345"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Solucionando erros de entrada no Skype for Business Online para administradores

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Para solucionar erros de entrada no Skype for Business Online, comece eliminando as causas mais comuns de dificuldade de entrada. Se necessário, você pode seguir etapas de resolução específicas com base no tipo de erro. Se o usuário ainda não conseguir entrar, colete informações adicionais e, em seguida, procure ajuda adicional.

## <a name="what-do-you-want-to-do"></a>O que você deseja fazer?
<a name="top"> </a>

> [Verificar as causas comuns dos erros de entrada no Skype for Business Online](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [Seguir etapas de resolução para um erro específico (somente para Empresas)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [Adicionar uma entrada de firewall para msoidsvc.exe ao seu servidor proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [Atualizar configurações de DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [Instalar um certificado SSL de terceiro no seu servidor ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [Atualizar credenciais de segurança](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [Modificar as chaves do registro TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [Atualizar configurações de usuários no Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [Usar o guia de solução de problemas do Suporte da Microsoft](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [Coletar mais informações e buscar ajuda adicional](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Verificar as causas comuns dos erros de entrada do Skype for Business Online
<a name="toc323194094"> </a>

A maioria dos problemas de entrada pode ser atribuída a um pequeno número de causas, e muitas delas são fáceis de corrigir. A tabela abaixo lista algumas causas comuns de erros de entrada e algumas etapas que você ou os usuários podem realizar para resolvê-los.


| **Possível Causa**                                                                                                                                                    | **Resolução**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Durante a entrada, é exibida uma caixa de diálogo que contém a seguinte frase: **não é possível verificar se o servidor é confiável para o seu endereço de entrada. Conectar-se mesmo assim?** <br/> | Verifique se o nome de domínio na caixa de diálogo é um servidor confiável em sua organização - por exemplo, **domainName.contoso.com**. Peça ao usuário para marcar a caixa de seleção **Sempre confiar neste servidor** e clique em **Conectar**. <br/> Os clientes corporativos podem impedir que essa mensagem apareça quando um usuário entrar pela primeira vez modificando o registro do Windows no computador de cada usuário. Para obter detalhes, consulte [Modificar chaves de registro TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
| Endereço de entrada, nome de usuário ou senha digitado incorretamente  <br/>                                                                                                               | Confirme se o nome de entrada e a senha do usuário estão corretos. <br/>  Verifique se o nome de entrada do usuário está formatado da seguinte maneira: <strong>bobk@contoso.com</strong>. Esse formato pode ser diferente daquele que você usa para entrar na rede da sua organização.  <br/>  Peça ao usuário para tentar entrar novamente. <br/>                                                                                                                                                                                                                             |
| Senha esquecida  <br/>                                                                                                                                             | Redefina a senha do usuário e notifique-o da nova senha temporária.  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Não licenciado para usar o Skype for Business Online  <br/>                                                                                                                  | Confirme se o usuário está registrado como um usuário do Skype for Business Online. Caso contrário, registre o usuário e peça que ele ou ela entre novamente.  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| Versão incorreta do Skype for Business Online instalada  <br/>                                                                                                           | Este problema geralmente está associado a uma mensagem de erro que contém a seguinte frase: **o serviço de autenticação pode ser incompatível com esta versão do programa.**.  <br/> Peça ao usuário para desinstalar e reinstalar o Skype for Business Online desde o Centro de administração do Microsoft 365.  <br/>                                                                                                                                                                                                                                                    |
| Problema ao adquirir um certificado pessoal que é necessário para entrar  <br/>                                                                                           | Se o endereço de entrada do usuário foi alterado recentemente, ele pode precisar excluir dados de entrada em cache. Peça aos usuários que saiam, cliquem no link Excluir minhas informações de entrada na tela de entrada e tentem novamente.  <br/>                                                                                                                                                                                                                                                                                                                                |
| Você configura um nome de domínio personalizado, e as mudanças podem não ter terminado de se propagar no sistema.  <br/>                                                         | Primeiro, verifique se você modificou os registros DNS (Domain Name Service) para refletir a alteração.  <br/> Se você já fez as alterações necessárias no DNS, avise o usuário para tentar entrar mais tarde. Alterações no DNS podem levar até 72 horas para serem refletidas em todo o sistema.  <br/>                                                                                                                                                                                                                                                        |
| Relógio do sistema fora de sincronização com o relógio do servidor  <br/>                                                                                                                     | Verifique se o controlador de domínio da rede está sincronizando com uma fonte de tempo externa confiável. Para obter detalhes, consulte o artigo 816042 da Base de Dados de Conhecimento da Microsoft, [Como configurar um servidor de horário autoritativo no Windows Server](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/>                                                                                                                                                                                                                                          |

Para solucionar erros de entrada no Skype for Business Online, comece eliminando as causas mais comuns de dificuldade de entrada. Se necessário, você pode seguir etapas de resolução específicas com base no tipo de erro. Se o usuário ainda não conseguir entrar, colete informações adicionais e, em seguida, procure ajuda adicional.

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Seguir etapas de resolução para um erro específico (somente para Empresas)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Estas instruções destinam-se principalmente a clientes do Microsoft Office 365 Plano E. Se você for um cliente do Office 365 Plano P, continue na seção a seguir, [Colete mais informações e procure ajuda adicional](troubleshooting-sign-in-errors-for-admins.md#collect-more-information).

Se o usuário não conseguir entrar depois de ter tentado as sugestões da seção anterior, você poderá fazer uma solução de problemas adicional com base no tipo de erro. A tabela abaixo lista as mensagens de erro mais comuns e possíveis causas. Seguindo a tabela, há procedimentos detalhados para abordar cada questão.

|**Mensagem de erro**|**Possível causa**|**Resolução**|
|:-----|:-----|:-----|
|Endereço de entrada não encontrado  <br/> |As solicitações de entrada do Assistente de Entrada do Microsoft Online Services (msoidsvc.exe) não estão sendo processadas por meio de seu firewall externo ou servidor proxy.  <br/> |[Adicionar uma entrada de firewall para msoidsvc.exe ao seu servidor proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|O servidor está temporariamente indisponível  <br/> |Se a sua organização tiver um domínio personalizado, as configurações necessárias de DNS (Sistema de Nome de Domínio) podem estar ausentes ou incorretas.  <br/> |[Atualizar configurações de DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|O servidor está temporariamente indisponível  <br/> |Se a sua organização estiver usando logon único com o Serviços de Federação do Active Directory (ADFS), você talvez tenha usado um certificado SSL autoassinado, em vez de uma autoridade de certificação de terceiro.  <br/> |[Instalar um certificado SSL de terceiro no seu servidor ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Problema ao adquirir um certificado pessoal que é necessário para entrar  <br/> |Se você já removeu os dados do servidor em cache usados para entrar e o erro continua a aparecer, as credenciais de segurança do usuário podem estar corrompidas, ou uma pasta RSA no computador do usuário pode estar bloqueando a autenticação.  <br/> |[Atualizar credenciais de segurança](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Uma caixa de diálogo de confiança de certificado é exibida quando um usuário entra pela primeira vez.  <br/> |Essa caixa de diálogo é exibida se o seu servidor do Skype for Business ainda não estiver listado na chave do Registro **TrustModelData**. <br/> |[Modificar as chaves do registro TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|O usuário não está habilitado para SIP  <br/> |Se a sua organização tiver uma instalação anterior do Microsoft Office Communications Server ou do Microsoft Lync Server 2010, talvez você não tenha excluído seus usuários do servidor antes de desatribuí-los. Como resultado, o atributo **msRTCSIP-UserEnabled** ainda está definido como **FALSO** nos Serviços de Domínio do Active Directory. <br/> |[Atualizar configurações de usuários no Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Adicionar uma entrada de firewall para msoidsvc.exe ao seu servidor proxy
<a name="add-a-firewall"> </a>

Este procedimento é uma correção possível para a seguinte mensagem de erro: **Endereço de entrada não encontrado**.

> [!NOTE]
> As etapas a seguir pressupõem que você esteja usando o Microsoft Forefront Threat Management Gateway (TMG) 2010. Se você tiver uma solução de gateway da web diferente, use as configurações descritas na etapa 4 abaixo.


Para criar uma entrada do aplicativo para Msoidsvc.exe no Forefront TMG 2010, siga estas etapas:

1. No painel esquerdo do Forefront, clique em **Rede**.

2. Clique na guia **Rede**. Na guia **Tarefas**, no painel direito, clique em **Definir Configurações do Forefront TMG Client**.

3. Na caixa de diálogo **Configurações do Forefront TMG Client**, clique em **Novo**.

4. Na caixa de diálogo **Configuração de Entrada do Aplicativo**, configure as seguintes regras:

|**Aplicativo**|**Chave**|**Valor**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Desabilitar  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

Para obter detalhes, consulte o artigo 2409256 da Base de Dados de Conhecimento Microsoft. [Você não pode se conectar ao Skype for Business Online porque um firewall local bloqueia a conexão](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).

### <a name="update-dns-settings"></a>Atualizar configurações de DNS
<a name="update-dns-service"> </a>

Se a sua organização tiver um domínio personalizado, este procedimento será uma possível correção para a seguinte mensagem de erro **O servidor está temporariamente indisponível**.

- Contate seu registrador de nome de domínio para obter informações sobre como adicionar o seguinte registro CNAME ao seu domínio:

  - **Tipo de registro de DNS**: CNAME

  - **Nome**: sip

  - **Valor/Destino**: sipdir.online.lync.com

Para obter detalhes, consulte o artigo 2566790 da Base de Dados de Conhecimento da Microsoft, [Solucionando problemas de configuração do DNS do Skype for Business Online no Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Instalar um certificado SSL de terceiros no seu servidor ADFS
<a name="verify-upn-and"> </a>

Para instalar um certificado SSL de terceiro no servidor Active Domain Federation Services (ADFS), siga estas etapas:

1. Obtenha um certificado SSL de uma autoridade de certificação de terceiro, como VeriSign ou Thawte.

2. Instale o certificado no seu servidor ADFS usando o console de gerenciamento do ADFS.

### <a name="update-security-credentials"></a>Atualizar credenciais de segurança
<a name="update-security-credentials"> </a>

Este procedimento é uma possível correção para a mensagem de erro **Problema ao adquirir seu certificado pessoal requerido para entrar**.

Para eliminar possíveis problemas de certificados ou credenciais, primeiro renove o certificado do usuário no Gerenciador de Certificados do Windows. Para fazer isto, siga estes passos:

1. Abra o Gerenciador de Certificados do Windows. Para fazer isso, clique em **Iniciar**, clique em **Executar**, digite **certmgr.msc** e, em seguida, clique em **OK**.

2. Clique duas vezes em **Pessoal** e duas vezes em **Certificados**.

3. Classifique pela coluna **Emitido por** e procure um certificado que seja emitido pelo Communications Server.

4. Clique com o botão direito do mouse no certificado e, em seguida, clique em **Excluir**.

Em seguida, se o usuário estiver executando o Windows 7, remova suas credenciais armazenadas no Gerenciador de Credenciais do Windows. Para fazer isto, siga estes passos:

1. Clique em **Iniciar**, em **Painel de Controle** e clique em **Gerenciador do Credenciais**.

2. Localize o conjunto de credenciais usado para conectar-se ao Skype for Business Online.

3. Expanda o conjunto de credenciais e clique em **Remover do Cofre**.

4. Entre novamente e reinsira as credenciais do usuário.

Por fim, se o usuário ainda não conseguir entrar depois de atualizar suas credenciais, tente excluir a pasta RSA no computador do usuário, pois isso pode estar bloqueando a conclusão do processo de autenticação do usuário:

1. Entre no computador do usuário usando uma conta de administrador.

2. Se necessário, ative a opção de exibição de pastas **Mostrar arquivos ocultos**.

3. Digite o seguinte na barra de endereços do Explorador de Arquivos: **C:\\Documents and Settings\\Nome de usuário\\Application Data\\Microsoft\\Crypto\\RSA**, onde **_Nome de usuário_** é seu nome para entrar no Windows.

4. Exclua qualquer pasta que comece com o nome **S-1-5-21-** seguido por uma cadeia de números.

### <a name="modify-trustmodeldata-registry-keys"></a>Modifique as chaves do registro TrustModelData
<a name="modify-trustmodeldata-registry"> </a>

Quando um usuário entra pela primeira vez, ele pode receber uma caixa de diálogo com algo como o seguinte: **Não é possível verificar se o servidor é confiável para o seu endereço de entrada. Conectar-se mesmo assim?** Este é um recurso de segurança e não um erro. No entanto, você pode impedir que a caixa de diálogo apareça usando um Objeto de Política de Grupo (GPO) para atualizar as máquinas dos usuários com seu nome de domínio antes de entrar pela primeira vez. Para fazer isso, execute o seguinte procedimento:

- Crie e implante um GPO que acrescente seu nome de domínio do Skype for Business - por exemplo, domainName.contoso.com - ao valor atual de HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData.

> [!IMPORTANT]
>  Você deve *acrescentar* seu nome de domínio ao valor existente e não simplesmente substituí-lo.

Para obter detalhes, consulte o artigo 2531068 da Base de Dados de Conhecimento da Microsoft, o [Skype for Business (Lync) não pode verificar se o servidor é confiável para o seu endereço de entrada.](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)

### <a name="update-user-settings-in-active-directory"></a>Atualizar as configurações de usuário no Active Directory
<a name="update-user-settings"> </a>

Se a sua organização tiver uma instalação anterior do Microsoft Office Communications Server ou do Microsoft Lync Server 2010, talvez você não tenha excluído seus usuários do servidor antes de desatribuí-los. Como resultado, o atributo **msRTCSIP-UserEnabled** ainda está definido como **FALSO** nos Serviços de Domínio do Active Directory.

Para corrigir esse problema, siga estas etapas:

1. Atualize o atributo **msRTCSIP-UserEnabled** de todos os usuários afetados para **TRUE**.

2. Execute novamente a Ferramenta de Sincronização de Diretórios do Microsoft Online Services (DirSync). Para obter detalhes, consulte [Integre seus diretórios locais com o Azure Active Directory](/azure/active-directory/hybrid/whatis-hybrid-identity).

Para solucionar erros de entrada no Skype for Business Online, comece eliminando as causas mais comuns de dificuldade de entrada. Se necessário, você pode seguir etapas de resolução específicas com base no tipo de erro. Se o usuário ainda não conseguir entrar, colete informações adicionais e, em seguida, procure ajuda adicional.
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Usar o guia de solução de problemas do Suporte da Microsoft
<a name="toc325626447"> </a>

Se você ainda não conseguir resolver os problemas de entrada do usuário, confira as sugestões no artigo 2541980 da Base de Dados de Conhecimento da Microsoft, [Como solucionar problemas de entrada no Skype for Business Online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).

## <a name="collect-more-information-and-seek-additional-help"></a>Coletar mais informações e buscar ajuda adicional
<a name="collect-more-information"> </a>

Se você seguiu as orientações acima e ainda não conseguiu resolver seus problemas de entrada, você deve coletar informações adicionais e entrar em contato com o suporte técnico. Para fazer isso, siga estes passos:

1. Obtenha os arquivos de log e os detalhes do log de eventos do Windows na máquina do usuário. Para obter instruções passo a passo, consulte o tópico de ajuda do usuário final [Ativar logs de erros no Lync](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).

2. Envie os arquivos de log e informações detalhadas sobre o erro para o suporte técnico da Microsoft.

Pode ser solicitado que você forneça informações de diagnóstico adicionais instalando o kit de ferramentas de suporte de Diagnóstico e Log do Microsoft Online Services (MOSDAL) na máquina do usuário afetado. Para detalhes, consulte [Usando Kit de Ferramentas de Suporte MOSDAL](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).

Para solucionar erros de entrada no Skype for Business Online, comece eliminando as causas mais comuns de dificuldade de entrada. Se necessário, você pode seguir etapas de resolução específicas com base no tipo de erro. Se o usuário ainda não conseguir entrar, colete informações adicionais e, em seguida, procure ajuda adicional.

## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)
