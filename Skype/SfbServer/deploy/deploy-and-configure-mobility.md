---
title: Implantar e configurar a mobilidade para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artigo levará você pelas etapas para configurar uma instalação de Skype for Business Server existente para usar o serviço Mobility, permitindo que seus dispositivos móveis sejam capazes de tirar proveito dos recursos Skype for Business Server Mobility.
ms.openlocfilehash: b4ca8b229fb0d6fc15305bb15c32466a678955f3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865419"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Implantar e configurar a mobilidade para Skype for Business Server  
 
Este artigo levará você pelas etapas para configurar uma instalação de Skype for Business Server existente para usar o serviço Mobility, permitindo que seus dispositivos móveis sejam capazes de tirar proveito dos recursos Skype for Business Server Mobility.
  
Depois de analisar o [artigo Plan for Mobility for Skype for Business Server,](../plan-your-deployment/mobility.md) você deve estar pronto para prosseguir com as etapas abaixo para implantar o Mobility em seu ambiente Skype for Business Server ambiente. As etapas são as seguintes (e estamos incluindo nesta tabela uma lista de permissões):
  
|**Fase**|**Permissões**|
|:-----|:-----|
|[Criar registros DNS](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Admins de domínio  <br/> DNSAdmins  <br/> |
|[Modificar certificados](deploy-and-configure-mobility.md#ModCerts) <br/> |Administrador Local  <br/> |
|[Configurar o proxy inverso](deploy-and-configure-mobility.md#ConfigRP) <br/> |Administrador Local  <br/> |
|[Configurar a Descoberta Automática para Mobilidade com implantações híbridas](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Admins de domínio  <br/> |
|[Testar sua implantação de Mobilidade](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurar para notificações por push](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurar política de mobilidade](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Todas as seções a seguir contêm etapas que pressuem que você leu o tópico Planejamento. Se algo estiver confundindo você, sinta-se à vontade para conferir as informações lá.

> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
## <a name="create-dns-records"></a>Criar registros DNS
<a name="CreateDNSRec"> </a>

Você pode já ter isso como parte do seu ambiente Skype for Business Server, mas precisa criar os seguintes registros para que a Descoberta Automática funcione:
  
- Um registro DNS interno para dar suporte a usuários móveis que estão se conectando de dentro da rede da sua organização.
    
- Um registro DNS externo (ou público) para dar suporte a usuários móveis que estão se conectando de fora da rede da sua organização.
    
Esses registros podem ser nomes A (host) ou registros CNAME (você não precisa fazer ambos, estamos apenas incluindo as etapas para tudo aqui).
  
### <a name="create-an-internal-dns-cname-record"></a>Criar um registro CNAME DNS interno

1. Faça logoff em um servidor DNS em sua  rede que seja membro do grupo Administradores de Domínio ou do **grupo DnsAdmins.**
    
2. Clique **em** Iniciar, Escolha Ferramentas  Administrativas (talvez seja necessário pesquisar se não for uma opção fora do menu Iniciar) e clique em **DNS** para abrir o snap-in administrativo DNS. 
    
3. No painel esquerdo da janela do console, você precisará ir para o domínio que está em casa para os Servidores Front-End do seu Skype for Business Server e expandir as **Zonas** de Visão Frontal.
    
4. Aproveite para ver qual das seguintes informações você tem:
    
   - Quaisquer registros de host A ou AAAA para o servidor front-end (Standard ou Enterprise) ou pools de front-end.
    
   - Qualquer host A ou AAAA registra um pool de Diretores ou Diretores (uma configuração opcional que você pode ter em sua implantação).
    
5. Depois de notá-lo, clique com o botão direito do mouse no nome de domínio SIP e escolha **Novo Alias (CNAME)** no menu.
    
6. Na caixa **de texto Nome** de alias, digite lyncdiscoverinternal para seu nome de host, para a URL interna do serviço de Descoberta Automática.
    
7. No **FQDN (nome** de domínio totalmente qualificado para host de destino), você precisará digitar ou navegar até o FQDN interno dos Serviços Web para seu pool de Front-End (ou servidor front-end único, ou pool de Diretor ou Diretor), identificado na etapa 4 acima. Clique em OK quando isso for inserido.
    
8. Você precisará criar um novo registro CNAME de Descoberta Automática na zona de busca de encaminhamento para cada domínio SIP com suporte em seu ambiente Skype for Business Server.
    
### <a name="create-an-external-dns-cname-record"></a>Criar um registro CNAME DNS externo

1. Essas etapas são genéricas, porque não podemos dizer qual provedor dns público você pode estar usando, mas ainda queremos ajudá-lo. Faça logoff em seu provedor DNS público com uma conta que poderá fazer novos registros DNS lá.
    
2. Neste momento, um domínio SIP já deve existir para Skype for Business Server. Expanda **a Zona de Busca Para Frente** para este domínio SIP ou abra-a de outra forma.
    
3. Aproveite para ver qual das seguintes informações você tem:
    
   - Quaisquer registros de host A ou AAAA para o servidor front-end (Standard ou Enterprise) ou pools de front-end.
    
   - Qualquer host A ou AAAA registra um pool de Diretores ou Diretores (uma configuração opcional que você pode ter em sua implantação).
    
4. Depois de ter essas informações, você deve ser capaz de selecionar uma opção para criar um **novo alias (CNAME)**.
    
5. Agora você deve poder inserir um **Nome** de Alias , você precisa inserir o lyncdiscover aqui para a URL de serviço de Descoberta Automática externa.
    
6. Em seguida, deve haver uma área para inserir em um **FQDN** para host de destino , isso precisará ser o FQDN para seu pool de Front-End (ou servidor front-end único, ou pool de Diretores ou Diretor), identificado na etapa 3 acima.
    
7. Talvez seja necessário salvar aqui ou, se precisar criar registros CNAME adicionais na zona de análise de encaminhamento de cada domínio SIP em seu ambiente de Skype for Business Server, faça isso, mas, quando estiver pronto, salve seu trabalho.
    
### <a name="create-an-internal-dns-a-record"></a>Criar um registro DNS A interno

1. Faça logoff em um servidor DNS em sua  rede que seja membro do grupo Administradores de Domínio ou do **grupo DnsAdmins.**
    
2. Clique **em** Iniciar, Escolha Ferramentas  Administrativas (talvez seja necessário pesquisar se não for uma opção fora do menu Iniciar) e clique em **DNS** para abrir o snap-in administrativo DNS. 
    
3. No painel esquerdo da janela do console, você precisará ir para o domínio que está em casa para os Servidores Front-End do seu Skype for Business Server e expandir as **Zonas** de Visão Frontal.
    
4. Aproveite para ver qual das seguintes informações você tem:
    
   - Quaisquer registros de host A ou AAAA para o servidor front-end (Standard ou Enterprise) ou pools de front-end.
    
   - Qualquer host A ou AAAA registra um pool de Diretores ou Diretores (uma configuração opcional que você pode ter em sua implantação).
    
5. Depois de notá-lo, clique com o botão direito do mouse no nome de domínio SIP e escolha **Novo Host (A ou AAAA)** no menu.
    
6. Na caixa **de texto** Nome, digite lyncdiscoverinternal para seu nome de host, para a URL interna do serviço de Descoberta Automática.
    
7. Na caixa **de texto Endereço IP,** digite o endereço IP dos Serviços Web internos para seu pool de Front-End (ou servidor front-end único, ou pool de Diretores ou Diretores), identificado na etapa 4 acima.
    
8. Quando isso for feito, clique em **Adicionar Host** e clique em **OK**.
    
9. Você precisará criar um novo registro A ou AAAA de Descoberta Automática na zona de busca de encaminhamento para cada domínio SIP com suporte em seu ambiente Skype for Business Server. Para fazer isso, repita as etapas de 6 a 8 quantas vezes for necessário.
    
10. Quando terminar, clique em **Feito**.
    
### <a name="create-an-external-dns-a-record"></a>Criar um registro DNS A externo

1. Essas etapas são genéricas, porque não podemos dizer qual provedor dns público você pode estar usando, mas ainda queremos ajudá-lo. Faça logoff em seu provedor DNS público com uma conta que poderá fazer novos registros DNS lá.
    
2. Neste momento, um domínio SIP já deve existir para Skype for Business Server. Expanda **a Zona de Busca Para Frente** para este domínio SIP ou abra-a de outra forma.
    
3. Aproveite para ver qual das seguintes informações você tem:
    
   - Quaisquer registros de host A ou AAAA para o servidor front-end (Standard ou Enterprise) ou pools de front-end.
    
   - Qualquer host A ou AAAA registra um pool de Diretores ou Diretores (uma configuração opcional que você pode ter em sua implantação).
    
4. Depois de ter essas informações, você deve ser capaz de selecionar uma opção para criar um **Novo Host A ou AAAA**.
    
5. Agora você deve poder inserir um **Nome**, você precisa inserir o lyncdiscover aqui para a URL de serviço de Descoberta Automática externa.
    
6. Em seguida, deve haver uma área para inserir um **Endereços IP,** que precisará ser o IP do pool de Front-End (ou servidor front-end único, ou pool de Diretores ou Diretor), identificado na etapa 3 acima.
    
7. Talvez você precise salvar aqui ou se precisar criar registros A ou AAAA adicionais na zona de busca de encaminhamento de cada domínio SIP para seu ambiente de Skype for Business Server, você deve fazer isso, mas quando estiver pronto, salve seu trabalho.
    
## <a name="modify-certificates"></a>Modificar certificados
<a name="ModCerts"> </a>

Se você tiver dúvidas sobre o Planejamento em torno de certificados, documentamos isso em nosso artigo [Plan for Mobility for Skype for Business Server.](../plan-your-deployment/mobility.md) Depois de analisar isso, vamos fazer o seguinte:
  
- Preciso de novos certificados?
    
- Solicitando novos certificados de sua Autoridade de Certificação (CA).
    
- Atualizando seus certificados in-locar com as substituições usando o PowerShell.
    
- Verificando os certificados usando o snapin Certificates no Console de Gerenciamento da Microsoft (MMC).
    
### <a name="do-i-need-new-certificates"></a>Preciso de novos certificados?

1. Primeiro, talvez seja necessário verificar e ver quais certificados estão no local e se eles têm ou não as entradas de que você precisa. Para fazer isso, você precisará fazer logoff no seu Skype for Business Server com uma conta que seja um Administrador local. Essa conta também pode precisar ter direitos para a Autoridade de Certificação (CA) em emissão, para algumas dessas etapas.
    
2. Abra o Skype for Business Server Shell de Gerenciamento (você pode usar a Pesquisa para encontrá-lo se não o tiver fixado em sua menu Iniciar ou barra de tarefas).
    
3. Será essencial que você saiba quais certificados foram atribuídos antes de tentar adicionar um certificado atualizado. Portanto, no comando, digite:
    
   ```powershell
   Get-CsCertificate
   ```

4. As informações da Etapa 3 serão exclusivas para você. Você precisa procurar para determinar se você tem um único certificado que foi atribuído a várias coisas ou se você tem um certificado diferente atribuído para os diferentes componentes que precisam delas. O **parâmetro Use** dirá como um certificado está sendo usado e o parâmetro **Thumbprint** dirá se é todo o mesmo certificado ou vários certificados.
    
5. Se você tiver as entradas SAN recomendadas em nossa seção Planejamento, você é bom. Caso não seja, você precisará solicitar um novo certificado ou vários certificados (dependendo da configuração) de sua Autoridade de Certificação.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Solicitar um novo certificado, ou certificados, de sua Autoridade de Certificação (CA)

1. Depois de verificar quais entradas san você tem, você sabe que tem um único certificado **(depois** de verificar através das etapas acima) e aprendeu que não tem todas as entradas necessárias. Uma nova solicitação de certificado precisa ser feita à sua AC. Abra seu Skype for Business Server PowerShell:
    
   - Para um SAN de Serviço de Descoberta Automática ausente (substituindo o parâmetro -Ca por seu próprio caminho de Autoridade de Certificação):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Agora, se você tiver vários domínios SIP, não poderá usar o parâmetro AllSipDomain como no exemplo acima. Em vez disso, você precisará usar o parâmetro DomainName. E quando você usa o parâmetro DomainName, precisa definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover. Um exemplo seria (substituindo o parâmetro -Ca pelo seu próprio caminho de Autoridade de Certificação):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Ou, depois de verificar quais entradas san você tem, você descobriu que tem vários **certificados** que não têm todas as entradas de que você precisa. Uma nova solicitação de certificado precisa ser feita à sua AC. Abra seu Skype for Business Server PowerShell:
    
   - Para um SAN de Serviço de Descoberta Automática ausente (substituindo o parâmetro -Ca por seu próprio caminho de Autoridade de Certificação):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Agora, se você tiver vários domínios SIP, não poderá usar o parâmetro AllSipDomain como no exemplo acima. Em vez disso, você precisará usar o parâmetro DomainName. E quando você usa o parâmetro DomainName, precisa definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover. Exemplos seriam (substituindo o parâmetro -Ca pelo seu próprio caminho de Autoridade de Certificação):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Depois que os novos certificados foram gerados pela AC, você precisará atribuí-los.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Atribuir certificados usando Skype for Business Server Shell de Gerenciamento

- Dependendo do que você encontrou na seção Do I need new certifications above, você precisa executar **uma** das seguintes.
    
  - Se você tiver um único certificado para tudo (as impressões digitais são idênticas), você precisará executar isso:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Se você tiver certificados diferentes para coisas (as impressões digitais são todas diferentes), execute isso em vez disso:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Exibindo certificados no Console de Gerenciamento da Microsoft (MMC)

1. Você tem uma opção para ver seus certificados usando o snap-in Certificados para o MMC. Basta digitar MMC na pesquisa e ele deve aparecer como uma opção de aplicativo,.
    
2. Para adicionar o snap-in Certificados, você precisará clicar em **Arquivo** e, em seguida, **Adicionar/Remover Snap-In...** (ou atalho de teclado **Ctrl+M** também funcionaria). **Certificados** serão uma opção no painel esquerdo, selecione-o e, em seguida, Conta de Computador na janela pop-up, em **seguida, Next**. 
    
3. Ainda na janela pop-up, é provável que você esteja fazendo isso no computador que está em casa para os certificados que você precisa ver, portanto, deixe a seleção no Computador **Local,** se for o caso. Se você estiver trabalhando em uma máquina remota, altere o botão de opção para Outro  Computador e insira o FQDN desse computador ou use o botão Procurar para pesquisar por esse computador por meio do AD.  Depois de selecionar o computador, você precisará clicar em **Concluir** quando estiver pronto **e,** em seguida, OK para adicionar o snap-in ao MMC.
    
4. Expanda **a seção Certificados** no painel esquerdo do MMC. Expanda **a pasta Pessoal** também e selecione **Certificados**. Isso permite que você veja os certificados neste armazenamento.
    
5. Você precisa localizar o certificado que deseja exibir, clicar com o botão direito do mouse nele e escolher **Abrir**.
    
    > [!NOTE]
    > Como você sabe que certificado é esse? Ele deve ser o único certificado atribuído a tudo para seu farm ou você pode ter vários certificados para coisas diferentes, como Default, Internal Web Services, etc., nesse caso, talvez seja necessário olhar para vários certificados. Vários certificados terão a mesma impressão digital. 
  
6. Depois de chegar ao ponto de exibição **Certificado,** escolha **Detalhes**. Isso permitirá que você veja o nome do assunto do certificado quando você selecionar **Assunto**, e o nome do assunto atribuído e as propriedades associadas são mostrados.
    
7. Você também precisará verificar as entradas **Nome Alternativo** do Assunto. Você encontrará um ou mais dos seguintes:
    
   - O nome do pool para esse pool ou o nome do servidor único se não for um pool.
    
   - O nome do servidor ao que o certificado é atribuído.
    
   - Registros de URL simples, geralmente atendem e discagem.
    
   - Nomes externos internos e serviços Web (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas escolhas feitas no Construtor de Topologias e seleções de Serviços Web sobrecarráveis.
    
   - Se já tiver sido atribuído, a descoberta lyncdiscover.\<sipdomain\> e lyncdiscoverinternal.\<sipdomain\> records.
    
     Você precisará verificar vários certificados se tiver mais de um atribuído (verifique a Observação acima).
    
8. Portanto, se você encontrar lyncdiscover.\<sipdomain\> e lyncdiscoverinternal.\<sipdomain\> records, você já configurou isso. Você pode fechar o MMC.
    
9. Se eles não são atribuídos, você precisará fazer uma nova solicitação de certificado (descrita acima) ou instalá-las após a solicitação (recomendamos o seguinte PowerShell acima para isso).
    
## <a name="configure-the-reverse-proxy"></a>Configurar o proxy inverso
<a name="ConfigRP"> </a>

As etapas a seguir não devem ser seguidas exatamente. Isso acontece porque nas versões anteriores do produto, nós o veríamos, por exemplo, configurando o Gateway de Gerenciamento de Ameaças (TMG) e, se você não estivesse usando isso, precisaria trabalhar sua própria versão a partir daí.
  
O TMG não está mais sendo oferecido pela Microsoft como produto e, se você ainda precisar configurá-lo, poderá ver as etapas do [Lync Server 2013.](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility) Mas as informações a seguir se destinam a ser mais geralmente úteis, mesmo que não haja nenhuma maneira de fornecermos etapas passo a passo específicas para cada proxy reverso lá fora.
  
Temos duas coisas principais a considerar:
  
- Você fará sua solicitação inicial de Descoberta Automática por HTTPS (o que recomendamos)?
    
  - Se você tiver uma regra de publicação na Web, precisará modificá-la.
    
  - Se você ainda não tiver uma regra de publicação na Web, será necessário crie-la.
    
- Se você estiver fazendo sua solicitação inicial de Descoberta Automática por HTTP, precisará criar ou modificar essa regra também.
    
> [!NOTE]
> **Importante** Um valor de tempo de tempo de tempo de proxy é um número que variará de implantação para implantação. Você deve monitorar sua implantação e modificar o valor da melhor experiência para clientes. Você pode ser capaz de definir o valor como 200. Se você estiver dando suporte a clientes móveis do Lync em seu ambiente, deverão definir o valor como 960 para permitir os tempos de notificação por push do Office 365, que têm um valor de tempo de tempo de 900. É muito provável que você tenha que aumentar o valor de tempo-de-tempo para evitar desconectar o cliente quando o valor for muito baixo ou diminuir o número se as conexões por meio do proxy não se desconectarem, mas desconectarem muito depois que o cliente se desconectar. Monitorar e basear o que é normal para seu ambiente é a única maneira precisa de determinar a configuração apropriada para esse valor.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificar a regra de publicação da Web existente para a SAN e a URL externas de Descoberta Automática

1. Abra sua interface de proxy reverso.
    
2. Você precisará localizar a regra de publicação da Web e escolher a opção Editar (pode estar em um menu ou guia, dependendo da configuração de proxy reverso).
    
3. Deve haver uma área em que esta regra de publicação da Web seja aplicada. Você precisa modificar essa regra para sites de entrada ou solicitações para sites. Você adicionará **uma** nova entrada.
    
4. Digite o nome do seu site de Descoberta Automática (o exemplo que vamos usar é lyncdiscover.contoso.com) e clique em **OK** ou **Salvar,** dependendo do formato do proxy Reverso.
    
5. Você pode ter um novo certificado que tenha a entrada SAN de Descoberta Automática nele. Isso também precisa ser instalado e configurado para uso de acordo com as configurações do proxy Reverso. Certifique-se de salvar tudo quando a configuração for concluída.
    
6. Se o proxy Reverso tiver uma funcionalidade **test,** faça uso dele para garantir que tudo está funcionando corretamente.
    
7. Agora, talvez seja necessário repetir essas etapas se você tiver um pool de Diretores ou Diretores em seu ambiente (isso significa que você tem uma segunda regra).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Criar uma regra de publicação da Web para a URL de Descoberta Automática externa

1. Abra sua interface de proxy reverso.
    
2. Você precisará localizar onde, na interface, criar suas regras de  publicação  da Web e escolher a opção Novo ou Criar (pode estar em um menu ou guia, dependendo da configuração de proxy reverso). Você está procurando a opção para criar uma nova regra de publicação da Web.
    
3. Normalmente, você precisará inserir as seguintes informações:
    
   - **Nome**: o nome da sua regra
    
   - **Ação de Regra**: Nesse caso, é uma **regra Permitir,** você está deixando algo passar pelo proxy Reverso.
    
   - A **regra de** publicação ou a opção que você está escolhendo seria site único ou **balanceador de carga.**
    
   - Isso precisa ser **SSL** para acesso externo, escolha essa opção.
    
   - Você precisará publicar um caminho para Publicação Interna **e** inserir o FQDN para os Serviços Web externos no balanceador de carga do pool de Front-End (ou o FQDN do balanceador de carga do pool de diretores, se você tiver um), um exemplo seria sfb_pool01.contoso.local.
    
   - Você deve digitar _ como o caminho a ser publicado, mas também precisa **/\\** _*encaminhar o header do host original**.
    
   - Haverá uma opção para detalhes ou informações **de** nomes públicos ou externos. Este é o local onde você poderá inserir:
    
   - **Aceite solicitações**, mas deve ser para o nome de domínio.
    
   - Para o **nome**, você deve inserir **lyncdiscover.**\<sipdomain> (esta é a URL externa do Serviço de Descoberta Automática). Agora, se você estiver criando uma regra para a URL de Serviços Web externos no pool de Front-End, você precisará digitar o FQDN para os Serviços Web externos em seu pool de Front-End (por exemplo, lyncwebextpool01.contoso.com).
    
   - Haverá uma opção **Path** e você precisará inserir **/\\** * aqui.
    
   - Você precisará selecionar um Ouvinte **SSL** com seu certificado público atualizado.
    
   - **A Delegação** de Autenticação deve ser definida como **Sem delegação**, mas a autenticação direta do cliente **deve** ser permitida.
    
   - A regra deve ser definida como **Todos os usuários**.
    
   - Essas devem ser todas as informações necessárias para criar essa regra e permitir que você prossiga.
    
4. Você precisará garantir que o **header do host original** seja encaminhado.
    
5. As **portas do Servidor** Web também precisarão ser definidas, você precisará fazer o seguinte:
    
   - **As solicitações de redirecionamento para a porta HTTP** e o número da porta devem ser **8080**.
    
   - **As solicitações de redirecionamento para a porta SSL** e o número da porta devem ser **4443**.
    
6. Quando tudo estiver configurado, você precisará salvá-los ou aplicá-los e, em seguida, testar a regra.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Criar uma regra de publicação da Web para a porta 80 (Opcional)

1. Abra sua interface de proxy reverso.
    
2. Você precisará localizar onde, na interface, criar suas regras de  publicação  da Web e escolher a opção Novo ou Criar (pode estar em um menu ou guia, dependendo da configuração de proxy reverso). Você está procurando a opção para criar uma nova regra de publicação da Web.
    
3. Normalmente, você precisará inserir as seguintes informações:
    
   - **Nome**: o nome da sua regra
    
   - **Ação de Regra**: Nesse caso, é uma **regra Permitir,** você está deixando algo passar pelo proxy Reverso.
    
   - A **regra de** publicação ou a opção que você está escolhendo seria site único ou **balanceador de carga.**
    
   - Isso precisa ser uma conexão não protegida para se conectar ao servidor **Web ou farm publicado.**
    
   - Você precisará publicar um caminho para Publicação Interna **e** inserir o FQDN para o endereço **VIP** do balanceador de carga do pool de Front-End, um exemplo seria sfb_pool01.contoso.local.
    
   - Você deve digitar _ como o caminho a ser publicado, mas também precisa **/\\** _*encaminhar o header do host original**.
    
   - Haverá uma opção para detalhes ou informações **de** nomes públicos ou externos. Este é o local onde você poderá inserir:
    
   - **Aceite solicitações**, mas deve ser para o nome de domínio.
    
   - Para o **nome**, você deve inserir **lyncdiscover.**\<sipdomain> (esta é a URL externa do Serviço de Descoberta Automática).
    
   - Haverá uma opção **Path** e você precisará inserir **/\\** * aqui.
    
   - Você precisará selecionar um ouvinte da Web ou permitir que seu proxy Reverso crie um para você.
    
   - **A Delegação** de Autenticação deve ser definida como **Nenhuma delegação**, mas a autenticação direta do cliente **não deve** ser permitida.
    
   - A regra deve ser definida como **Todos os usuários**.
    
   - Essas devem ser todas as informações necessárias para criar essa regra e permitir que você prossiga.
    
4. As **portas do Servidor** Web precisarão ser definidas, você precisará fazer o seguinte:
    
   - **As solicitações de redirecionamento para a porta HTTP** e o número da porta devem ser **8080**.
    
   - **As solicitações de redirecionamento para a porta SSL** e o número da porta devem ser **4443**.
    
5. Quando tudo estiver configurado, você precisará salvá-los ou aplicá-los e, em seguida, testar a regra.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurar a Descoberta Automática para Mobilidade com implantações híbridas
<a name="ConfigAutoD"> </a>

Ambientes híbridos Skype for Business Server ambientes que combinam um ambiente local e O365. Quando você Skype for Business Server trabalhando em um ambiente Híbrido, o serviço de Descoberta Automática precisa ser capaz de localizar um usuário de qualquer um desses ambientes.
  
Para permitir que os clientes móveis descubram onde um usuário está localizado, o serviço de Descoberta Automática precisa ser configurado com um novo localizador de recursos uniforme (URL). As etapas são:
  
1. Abra Skype for Business Server Shell de Gerenciamento.
    
2. Execute o seguinte para obter o valor do **atributo ProxyFQDN** para seu Skype for Business Server ambiente:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Em seguida, ainda na janela do shell, execute:
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Onde [identidade] é substituído pelo nome do domínio do espaço de endereço SIP compartilhado.
    
## <a name="test-your-mobility-deployment"></a>Testar sua implantação de Mobilidade
<a name="TestMobility"> </a>

Depois de ter implantado Skype for Business Server Mobility Service e Skype for Business Server Autodiscover Service, você vai querer executar uma transação de teste, para garantir que sua implantação está funcionando bem. Você pode executar **Test-CsUcwaConference** para testar a capacidade de dois usuários criarem, ingressarem e se comunicarem em uma conferência. Você precisará de dois usuários (reais ou de teste) e suas credenciais completas para fazer esse teste. Esse comando funcionará tanto para clientes Skype for Business quanto para clientes do Lync Server 2013.
  
Para clientes do Lync Server 2010 no Skype for Business Server 2015, você precisará executar **Test-CsMcxP2PIM** para testar. Os usuários do Lync Server 2010 ainda precisarão ser usuários reais ou usuários de teste predefinidos, e você precisará das credenciais de senha.

> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Test conferencing for Skype for Business e Lync 2013 mobile clients

1. Faça logon como membro da **função CsAdministrator** em qualquer computador onde Skype for Business Server **Shell** de Gerenciamento e **Ocscore** estão instalados.
    
2. Inicie o **Skype for Business Server Shell** de Gerenciamento (você pode digitar o nome na pesquisa ou ir para Todos os **Programas** e escolha-o).
    
3. Na linha de comando, digite:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Também é possível definir credenciais em um script e passá-las para o cmdlet de teste. Temos um exemplo disso abaixo.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Conferência de teste para clientes móveis do Lync 2010

> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.

1. Faça logon como membro da **função CsAdministrator** em qualquer computador onde Skype for Business Server **Shell** de Gerenciamento e **Ocscore** estão instalados.
    
2. Inicie o **Skype for Business Server Shell** de Gerenciamento (você pode digitar o nome na pesquisa ou ir para Todos os **Programas** e escolha-o).
    
3. Na linha de comando, digite:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Também é possível definir credenciais em um script e passá-las para o cmdlet de teste. Temos um exemplo disso abaixo.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Para revisar ainda mais os procedimentos de comando, você pode conferir [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference) e [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim).
  
## <a name="configure-for-push-notifications"></a>Configurar para notificações por push
<a name="ConfigPush"> </a>

As notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas para um dispositivo móvel mesmo quando o aplicativo Skype ou Lync estiver inativo. Mas o que são notificações por push? Eles são alertas de eventos, como um convite de IM novo ou perdido ou para uma caixa postal recebida. O serviço Skype for Business Server Mobility envia essas notificações para o Serviço de Notificação por Push Skype for Business Server baseado em nuvem, que envia as notificações para o Serviço de Notificação por Push da Microsoft (MSNS) para usuários Windows Phone.
  
Essa funcionalidade não é alterada do Lync Server 2013, mas se você tiver uma Skype for Business Server, faça o seguinte:
  
- Para um Skype for Business Server de Borda, adicione um novo provedor de hospedagem, o Microsoft Skype for Business Online, e, em seguida, configurar a federação do provedor de hospedagem entre sua organização e o Skype for Business Online.
    
- Habilita as notificações por push executando o cmdlet **Set-CsPushNotificationConfiguration.** Por padrão, as notificações por push estão desativadas.
    
- Teste sua configuração de federação e notificações por push.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurar seu Skype for Business de Borda para notificações por push

1. Faça logon, com uma conta membro da função **CsAdministrator,** para um computador onde o **Shell** de Gerenciamento e **o Ocscore** Skype for Business Server estão instalados.
    
2. Inicie o **Shell de Gerenciamento Skype for Business Server .**
    
3. Adicione um Skype for Business Server de hospedagem online.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Como exemplo:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Não é possível ter mais de uma relação de federação com um único provedor de hospedagem. Portanto, se você já tiver criado um provedor de hospedagem que tenha uma relação de federação com o sipfed.online.lync.com, não adicione outro provedor de hospedagem para ele, mesmo que a identidade do provedor de hospedagem seja algo diferente do SkypeOnline. 
  
4. Configurar a federação do provedor de hospedagem entre sua organização e o Serviço de Notificação por Push no Skype for Business Online. Na linha de comando, você precisará digitar:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Habilitar notificações por push

1. Faça logon, com uma conta membro da função **CsAdministrator,** para um computador onde o **Shell** de Gerenciamento e **o Ocscore** Skype for Business Server estão instalados.
    
2. Inicie o **Shell de Gerenciamento Skype for Business Server .**
    
3. Habilitar notificações por push:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Habilitar Federação:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Testar notificações por push e federação

1. Faça logon, com uma conta membro da função **CsAdministrator,** para um computador onde o **Shell** de Gerenciamento e **o Ocscore** Skype for Business Server estão instalados.
    
2. Inicie o **Shell de Gerenciamento Skype for Business Server .**
    
3. Teste a configuração de federação:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Como exemplo:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Teste suas notificações por push:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Como exemplo:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Configurar política de mobilidade
<a name="ConfigMob"> </a>

Você tem a capacidade de Skype for Business Server determinar quem pode usar seu serviço de Mobilidade, Chamada via Trabalho, IP de voz sobre IP (VoIP) ou vídeo, bem como se o WiFi será necessário para VoIP ou vídeo. A chamada via Trabalho permite que um usuário móvel use seu número de telefone comercial, em vez de seu número de telefone celular, ao fazer e receber chamadas. A pessoa do outro lado da linha não verá o número de telefone celular do usuário móvel e permite que o usuário móvel evite cobranças de chamada de saída. Quando o VoIP e o vídeo são definidos, os usuários podem fazer chamadas VoIP e vídeo. As configurações de uso wi-fi determinam se o dispositivo móvel de um usuário será necessário para usar uma rede WiFi em uma rede de dados celular.
  
Mobilidade, Chamada via Trabalho e os recursos voIP e vídeo estão todos habilitados por padrão. A configuração para exigir WiFi para VoIP e vídeo está desabilitada. Um Administrador tem a capacidade de alterar isso, globalmente, por site ou por usuário.
  
Para poder usar recursos de Mobilidade e Chamada via Trabalho, os usuários precisam ser:
  
- Habilitado para Skype for Business Server
    
- Habilitado para Enterprise Voice.
    
- Atribuída uma política de Mobilidade que tem a **opção EnableMobility** definida como **True**.
    
Para que os usuários sejam capazes de usar a Chamada via Trabalho, eles também precisarão ser:
  
- Atribuído uma política de voz que tem a **opção Habilitar toque simultâneo de telefones** selecionada.
    
- Atribuída uma política de Mobilidade que tem **o EnableOutsideVoice** definido como **True**.
    
> [!NOTE]
> Os usuários que não estão habilitados para o Enterprise Voice Skype podem usar seus dispositivos móveis para fazer chamadas voIP Skype Skype ou participar de conferências usando o link Clique para Ingressar em seus dispositivos móveis, se as opções apropriadas são definidas para a política de Voz à que estão associados. Há mais detalhes no tópico PLANEJAMENTO. 
  
### <a name="modify-global-mobility-policy"></a>Modificar a política de mobilidade global

1. Faça logon, com uma conta membro da função **CsAdministrator,** para um computador onde o **Shell** de Gerenciamento e **o Ocscore** Skype for Business Server estão instalados.
    
2. Inicie o **Shell de Gerenciamento Skype for Business Server .**
    
3. Desativar o acesso a Mobilidade e Chamada via Trabalho globalmente digitando:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Você pode desativar Call via Work sem desativar o acesso ao Mobility. Mas você não pode desativar o Mobility sem também desativar a Chamada via Trabalho. 
  
    Para obter mais informações, confira [Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy).
    
### <a name="modify-mobility-policy-by-site"></a>Modificar a política de mobilidade por site

1. Faça logon, com uma conta membro da função **CsAdministrator,** para um computador onde o **Shell** de Gerenciamento e **o Ocscore** Skype for Business Server estão instalados.
    
2. Inicie o **Shell de Gerenciamento Skype for Business Server .**
    
3. Você pode criar uma política no nível do site, desativar VoIP e vídeo, habilitar Exigir WiFi para Áudio IP e Exigir WiFi para Vídeo IP por site. Tipo:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Saiba mais em [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy).
    
### <a name="modify-mobility-policy-by-user"></a>Modificar a política de mobilidade pelo usuário

1. Faça logon, com uma conta membro da função **CsAdministrator,** para um computador onde o **Shell** de Gerenciamento e **o Ocscore** Skype for Business Server estão instalados.
    
2. Inicie o **Shell de Gerenciamento Skype for Business Server .**
    
3. Crie políticas de mobilidade no nível do usuário e desligue Mobility e Call via Work by user. Tipo:
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Outro exemplo com dados de exemplo:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Você pode desativar Call via Work sem desativar o acesso ao Mobility. Mas você não pode desativar o Mobility sem também desativar a Chamada via Trabalho. 
