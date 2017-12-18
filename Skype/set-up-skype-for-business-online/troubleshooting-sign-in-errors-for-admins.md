---
title: "Solução de problemas para erros de entrada do Skype for Business Online (administradores)"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
description: "Learn common causes for Skype for Business Online sign-errors and Work through troubleshooting these problems. "
---

# Solução de problemas para erros de entrada do Skype for Business Online (administradores)

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Para solucionar erros de entrada Skype for Business Online, comece eliminando as causas mais comuns de dificuldade de entrar. Se necessário, você poderá seguir resolução específica etapas com base no tipo de erro. Se o usuário ainda não conseguir entrar, coletar informações adicionais e, em seguida, buscar ajuda adicional.
  
## O que deseja fazer?
<a name="__top"> </a>

> [Verificar causas comuns de erros de entrada Skype for Business Online](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc323194094)
    
> [Seguir etapas de resolução para um erro específico (somente para Empresas)](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626440)
    
> [Adicionar uma entrada de firewall para msoidsvc.exe ao seu servidor proxy](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall)
    
> [Atualizar configurações de DNS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service)
    
> [Instalar um certificado SSL de terceiro no seu servidor ADFS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and)
    
> [Atualizar credenciais de segurança](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1)
    
> [Modificar as chaves do registro TrustModelData](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry)
    
> [Atualizar configurações de usuários no Active Directory](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1)
    
> [Usar o guia de solução de problemas do Suporte da Microsoft](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626447)
    
> [Coletar mais informações e buscar ajuda adicional](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1)
    
## Verificar causas comuns de erros de entrada Skype for Business Online
<a name="__toc323194094"> </a>

A maioria dos problemas de entrada podem ser rastreados para um pequeno número de causas e muitas delas são fáceis de corrigir. A tabela a seguir lista algumas causas comuns de erros de entrada e algumas etapas que você ou os usuários poderão ser tomadas para resolvê-los.
  
|**Possível Causa**|**Resolução**|
|:-----|:-----|
|Durante a entrar, aparece uma caixa de diálogo que contém a seguinte frase: **não consegue verificar se o servidor é confiável para seu endereço de entrada. Conectar-se mesmo assim?** <br/> |Verifique se o nome do domínio na caixa de diálogo é um servidor confiável na sua organização  por exemplo, **domainName.contoso.com**. Peça para o usuário marcar a caixa de seleção **Sempre confiar neste servidor** e depois clicar em **Conectar**. <br/> Clientes corporativos podem impedir a exibição dessa mensagem quando um usuário entra pela primeira vez, modificando o registro do Windows no computador de cada usuário. Para obter detalhes, veja [Modificar as chaves do registro TrustModelData](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry).  <br/> |
|Endereço de entrada, nome de usuário ou senha digitado incorretamente  <br/> | Confirme se o nome de entrada e a senha do usuário estão corretos. <br/>  Verifique se o nome de entrada do usuário está formatado da seguinte maneira: **bobk@contoso.com**. Esse formato pode ser diferente daquele que você usa para entrar na rede da sua organização.  <br/>  Peça para o usuário tentar entrar novamente. <br/> |
|Senha esquecida  <br/> |Redefina a senha do usuário e notifique-o da nova senha temporária.  <br/> |
|Não licenciado para usar Skype for Business Online  <br/> |Confirme que o usuário está registrado como um usuário Skype for Business Online. Caso contrário, registre o usuário e, em seguida, pedir que ele entrar novamente.  <br/> |
|Versão incorreta do Skype for Business Online instalado  <br/> |Este problema geralmente está associado a uma mensagem de erro que contém a seguinte frase: **o serviço de autenticação pode ser incompatível com esta versão do programa.**.  <br/> Peça para o usuário desinstalar e reinstalar Skype for Business Online no Portal do Office 365.  <br/> |
|Problema ao adquirir um certificado pessoal que é necessário para entrar  <br/> |Se o endereço de entrada do usuário foi alterada recentemente, eles talvez precise excluir dados de entrada em cache. Peça aos usuários para sair, clique no botão excluir minhas informações de entrada link na tela de entrada e tente novamente.  <br/> |
|Você configura um nome de domínio personalizado, e as mudanças podem não ter terminado de se propagar no sistema.  <br/> |Primeiro, certifique-se de que você modificou os registros do serviço de nome de domínio (DNS) para refletir a alteração.  <br/> Se você já tiver feito as alterações necessárias de DNS, oriente o usuário a tentar registrar em log posteriormente. As alterações de DNS podem levar até 72 horas para serem refletidas em todo o sistema.  <br/> |
|Relógio do sistema fora de sincronização com o relógio do servidor  <br/> |Verifique se o controlador de domínio da rede está sincronizando com uma fonte de horário externa confiável. Para obter detalhes, veja o artigo 816042 da Base de Dados de Conhecimento Microsoft: [Como configurar um servidor de horário autoritativo no Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).  <br/> |
   
[Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade. Para sua referência, veja a versão em inglês deste artigo aquihttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Para solucionar erros de entrada Skype for Business Online, comece eliminando as causas mais comuns de dificuldade de entrar. Se necessário, você poderá seguir resolução específica etapas com base no tipo de erro. Se o usuário ainda não conseguir entrar, coletar informações adicionais e, em seguida, buscar ajuda adicional.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Seguir etapas de resolução para um erro específico (somente para Empresas)
<a name="__toc325626440"> </a>

> [!IMPORTANT]
> Estas instruções estão destinadas principalmente para clientes do Microsoft Office 365 Plano E. Se você for um cliente do Office 365 Plano P, continue na seção seguinte, [Coletar mais informações e buscar ajuda adicional](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1). 
  
Se o usuário não conseguir entrar depois que você tiver tentado as sugestões na seção anterior, tente usar outras soluções com base no tipo de erro. A tabela abaixo lista as mensagens de erro mais comuns e as causas possíveis. Abaixo da tabela, estão os procedimentos detalhados para lidar com cada problema.
  
|**Mensagem de erro**|**Possível causa**|**Resolução**|
|:-----|:-----|:-----|
|Endereço de entrada não encontrado  <br/> |As solicitações de entrada do Assistente de Entrada do Microsoft Online Services (msoidsvc.exe) não estão sendo processadas por meio de seu firewall externo ou servidor proxy.  <br/> |[Adicionar uma entrada de firewall para msoidsvc.exe ao seu servidor proxy](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall) <br/> |
|O servidor está temporariamente indisponível  <br/> |Se a sua organização tiver um domínio personalizado, as configurações necessárias de DNS (Sistema de Nome de Domínio) podem estar ausentes ou incorretas.  <br/> |[Atualizar configurações de DNS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service) <br/> |
|O servidor está temporariamente indisponível  <br/> |Se a sua organização estiver usando logon único com o Active Directory Federation Services (ADFS), você talvez tenha usado um certificado SSL autoassinado, em vez de uma autoridade de certificação de terceiro.  <br/> |[Instalar um certificado SSL de terceiro no seu servidor ADFS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and) <br/> |
|Problema ao adquirir um certificado pessoal que é necessário para entrar  <br/> |Se você já tiver removido os dados do servidor em cache usados para entrar e o erro continua a aparecer, credenciais de segurança do usuário podem estar corrompidas ou uma pasta RSA no computador do usuário pode estar bloqueando a autenticação.  <br/> |[Atualizar credenciais de segurança](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1) <br/> |
|Uma caixa de diálogo de confiança de certificado é exibida quando um usuário entra pela primeira vez.  <br/> |Esta caixa de diálogo aparece se o servidor de Skype for Business ainda não está listado na chave do registro **TrustModelData**.  <br/> |[Modificar as chaves do registro TrustModelData](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry) <br/> |
|O usuário não está habilitado para SIP  <br/> |Se a sua organização tinha uma instalação anterior do Microsoft Office Communications Server ou do Microsoft Lync Server 2010, talvez você não tenha excluído seus usuários do servidor antes de desprogramá-lo. Como resultado, o atributo **msRTCSIP-UserEnabled** ainda está definido como **FALSE** nos Serviços de Domínio Active Directory. <br/> |[Atualizar configurações de usuários no Active Directory](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1) <br/> |
   
### Adicionar uma entrada de firewall para msoidsvc.exe ao seu servidor proxy
<a name="__add_a_firewall"> </a>

Este procedimento é uma correção possível para a seguinte mensagem de erro: **Endereço de entrada não encontrado**.
  
 **NOTA**: As etapas a seguir supõem que você esteja usando o Microsoft Forefront Threat Management Gateway (TMG) 2010. Se estiver usando uma solução de gateway da Web diferente, use as configurações descritas na etapa 4 a seguir.
  
Para criar uma entrada do aplicativo para Msoidsvc.exe no Forefront TMG 2010, siga estas etapas:
  
1. No painel esquerdo do Forefront, clique em **Rede**.
    
2. Clique na guia **Rede**. Na guia **Tarefas**, no painel direito, clique em **Definir Configurações do Forefront TMG Client**.
    
3. Na caixa de diálogo **Configurações do Forefront TMG Client**, clique em **Novo**.
    
4. Na caixa de diálogo **Configuração de Entrada do Aplicativo**, configure as seguintes regras:
    
|****Aplicativo****|****Tecla****|****Valor****|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Desabilitar  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
Para obter detalhes, consulte o artigo da Base de dados de Conhecimento Microsoft 2409256, [que é possível conectar ao Skype for Business Online porque um firewall local bloqueia a conexão](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).
  
### Atualizar configurações de DNS
<a name="__update_dns_service"> </a>

Se a sua organização tiver um domínio personalizado, este procedimento será uma possível correção para a seguinte mensagem de erro **O servidor está temporariamente indisponível**.
  
- Contate o registro de domínio do servidor para obter informações sobre como adicionar o seguinte registro CNAME ao seu domínio:
    
  - **Tipo de registro de DNS**: CNAME
    
  - **Nome**: sip
    
  - **Valor/Destino**: sipdir.online.microsoft.com
    
Para obter detalhes, consulte o artigo da Base de Conhecimento Microsoft 2566790, [Skype de solução de problemas para problemas de configuração de DNS de negócios Online no Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)e o artigo Wiki do Office 365, [assegurando que sua rede funciona com o Skype for Business (Lync) Online](https://go.microsoft.com/fwlink/?linkid=231156).
  
### Instalar um certificado SSL de terceiro no seu servidor ADFS
<a name="__verify_upn_and"> </a>

Para instalar um certificado SSL de terceiro no servidor Active Domain Federation Services (ADFS), siga estas etapas:
  
1. Obtenha um certificado SSL de uma autoridade de certificação de terceiro, como VeriSign ou Thawte.
    
2. Instale o certificado no seu servidor ADFS usando o console de gerenciamento do ADFS.
    
### Atualizar credenciais de segurança
<a name="__update_security_credentials_1"> </a>

Este procedimento é uma possível correção para a mensagem de erro **Problema ao adquirir seu certificado pessoal requerido para entrar**.
  
Para eliminar possíveis problemas de credenciais ou certificado, primeiro revise o certificado do usuário no Gerenciador de Certificados do Windows. Para fazer isso, execute as etapas seguintes:
  
1. Abra o Gerenciador de Certificados do Windows. Para fazer isso, clique em **Sim**, **Executar**, digite **certmgr.msc** e clique em **OK**.
    
2. Clique duas vezes em **Pessoal** e duas vezes em **Certificados**.
    
3. Classifique pela coluna **Emitido por** e procure um certificado que seja emitido pelo Communications Server.
    
4. Clique com o botão direito do mouse no certificado e, em seguida, clique em **Excluir**.
    
Em seguida, se o usuário estiver executando em Windows 7, remova suas credenciais armazenadas no Windows Credential Manager. Para fazer isso, execute as etapas seguintes:
  
1. Clique em **Iniciar**, em **Painel de Controle** e clique em **Gerenciador do Credenciais**.
    
2. Localize o conjunto de credenciais usado para conectar-se a Skype for Business Online.
    
3. Expanda o conjunto de credenciais e clique em **Remover do Cofre**.
    
4. Entre novamente e reinsira as credenciais do usuário.
    
Finalmente, se o usuário ainda não puder entrar após a atualização das credenciais, tente excluir a pasta RSA do computador do usuário, pois ela poderá estar bloqueando a conclusão do processo de autenticação do usuário:
  
1. Entre no computador do usuário usando uma conta de administrador.
    
2. Se necessário, ative a opção de modo de exibição de pasta **Mostrar arquivos ocultos**.
    
3. Digite o seguinte na barra de endereços do Explorador de Arquivos: **C:\\Documentos e Configurações\\NomedeUsuário\\Application Data\\Microsoft\\Crypto\\RSA**, **onde** ** *NomedeUsuário* ** **é o seu nome de entrada no Windows**.
    
4. Exclua qualquer pasta que comece com o nome **S-1-5-21-** seguido por uma cadeia de números.
    
### Modificar as chaves do registro TrustModelData
<a name="__modify_trustmodeldata_registry"> </a>

Quando um usuário entra pela primeira vez, ele podem receber uma caixa de diálogo que contém algo parecido com o seguinte: **não consegue verificar se o servidor é confiável para seu endereço de entrada. Conectar-se mesmo assim?** Este é um recurso de segurança e não um erro. No entanto, você pode impedir que a caixa de diálogo que aparecem, usando um objeto de política de grupo (GPO) para atualizar máquinas dos usuários com seu nome de domínio, antes que eles entrar pela primeira vez. Para fazer isso, faça o seguinte:
  
- Crie e implante um GPO que acrescente o seu nome de domínio Skype for Business  por exemplo, DomainName.contoso.com  ao valor correto de hkey_local_machine\\software\\policies\\microsoft\\communicator\\trustmodeldata..
    
> [!IMPORTANT]
> Você deve  *acrescentar*  seu nome de domínio ao valor existente, e não simplesmente substituí-lo.
  
Para detalhes, veja o artigo 2531068 da Base de Dados de Conhecimento Microsoft: [O Skype for Business (Lync) não pode verificar se o servidor é confiável para seu endereço de entrada](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).
  
### Atualizar configurações de usuários no Active Directory
<a name="__update_user_settings_1"> </a>

Se a sua organização tinha uma instalação anterior do Microsoft Office Communications Server ou do Microsoft Lync Server 2010, talvez você não tenha excluído seus usuários do servidor antes de desprogramá-lo. Como resultado, o atributo **msRTCSIP-UserEnabled** ainda está definido como **FALSE** nos Serviços de Domínio Active Directory.
  
Para corrigir esse problema, siga estas etapas:
  
1. Atualize o atributo **msRTCSIP-UserEnabled** de todos os usuários afetados para **TRUE**.
    
2. Execute a ferramenta de sincronização de diretórios do Microsoft Online Services (DirSync). Para obter detalhes, consulte [diretórios AIntegrate seu local com o Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).
    
[Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade. Para sua referência, veja a versão em inglês deste artigo aquihttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Para solucionar erros de entrada Skype for Business Online, comece eliminando as causas mais comuns de dificuldade de entrar. Se necessário, você poderá seguir resolução específica etapas com base no tipo de erro. Se o usuário ainda não conseguir entrar, coletar informações adicionais e, em seguida, buscar ajuda adicional.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Usar o guia de solução de problemas do Suporte da Microsoft
<a name="__toc325626447"> </a>

Se mesmo assim você não conseguir resolver problemas de entrada do usuário, confira as sugestões no artigo da Base de Conhecimento Microsoft 2541980, [como solucionar problemas de entrada no Skype for Business Online](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).
  
## Coletar mais informações e buscar ajuda adicional
<a name="__collect_more_information_1"> </a>

Se você seguiu as orientações acima e ainda não consegue resolver seus problemas de entrada, você deve coletar informações adicionais e contate o suporte técnico. Para fazer isso, siga estas etapas:
  
1. Obter os arquivos de log e detalhes de log de eventos do Windows do computador do usuário. Para obter instruções passo a passo, consulte o tópico de Ajuda do usuário final [Ativar logs de erro no Skype for Business (Lync)](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).
    
2. Envie os arquivos de log e informações detalhadas sobre o erro para o suporte técnico.
    
Talvez você seja solicitado a fornecer informações de diagnóstico adicionais, instalando o Kit de Ferramentas de Suporte MOSDAL (Diagnóstico e Log do Microsoft Online Services) no computador do usuário afetado. Para obter detalhes, veja o tópico sobre como [Usando o Kit de Ferramentas de Suporte MOSDAL](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).
  
[Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade. Para sua referência, veja a versão em inglês deste artigo aquihttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Para solucionar erros de entrada Skype for Business Online, comece eliminando as causas mais comuns de dificuldade de entrar. Se necessário, você poderá seguir resolução específica etapas com base no tipo de erro. Se o usuário ainda não conseguir entrar, coletar informações adicionais e, em seguida, buscar ajuda adicional.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

