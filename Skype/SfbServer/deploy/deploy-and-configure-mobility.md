---
title: Implantar e configurar o Mobility para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artigo guiará você pelas etapas para configurar uma instalação existente do Skype for Business Server para usar o serviço de mobilidade, permitindo que seus dispositivos móveis possam tirar proveito dos recursos de mobilidade do Skype for Business Server.
ms.openlocfilehash: 910e23e8aec18d36c3a7e4bda9e97828fb498802
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234570"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Implantar e configurar o Mobility para o Skype for Business Server  
 
Este artigo guiará você pelas etapas para configurar uma instalação existente do Skype for Business Server para usar o serviço de mobilidade, permitindo que seus dispositivos móveis possam tirar proveito dos recursos de mobilidade do Skype for Business Server.
  
Revisou o artigo [plano de mobilidade para o Skype for Business Server](../plan-your-deployment/mobility.md) , você deve estar pronto para continuar com as etapas abaixo para implantar a mobilidade no ambiente do Skype for Business Server. As etapas são as seguintes (e estamos incluindo nesta tabela uma lista de permissões):
  
|**Fase**|**Permissões**|
|:-----|:-----|
|[Criar registros DNS](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Admins. do Domínio  <br/> DNSAdmins  <br/> |
|[Modificar certificados](deploy-and-configure-mobility.md#ModCerts) <br/> |Administrador Local  <br/> |
|[Configurar o proxy inverso](deploy-and-configure-mobility.md#ConfigRP) <br/> |Administrador Local  <br/> |
|[Configurar Descoberta Automática para Mobilidade com implantações híbridas](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Admins. do Domínio  <br/> |
|[Testar a implantação de mobilidade](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurar para notificações por push](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurar a política de mobilidade](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Todas as seções a seguir contêm as etapas que você já deve ter lido no tópico sobre planejamento. Se tiver dúvidas, consulte esse tópico.

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
## <a name="create-dns-records"></a>Criar registros DNS
<a name="CreateDNSRec"> </a>

Você pode já ter isso como parte do seu ambiente do Skype for Business Server, mas precisa criar os seguintes registros para que o AutoDiscovery funcione:
  
- Um registro DNS interno para dar suporte a usuários móveis que se conectam através da rede da organização.
    
- Um registro DNS externo (ou público) para dar suporte a usuários móveis que se conectam de fora da rede da organização.
    
Esses registros podem ser nomes A (host) ou registros CNAME (você não precisa criar ambos, essas etapas são gerais).
  
### <a name="create-an-internal-dns-cname-record"></a>Para criar um registro CNAME de DNS interno:

1. Faça logon em um servidor DNS em uma rede que seja membro do grupo **Admins. do Domínio** ou do grupo **DnsAdmins**.
    
2. Clique em **Iniciar**, escolha **Ferramentas Administrativas** (talvez você precise **Pesquisar**, se ela for uma opção fora do menu Iniciar) e clique em **DNS** para abrir o snap-in administrativo do DNS.
    
3. No painel à esquerda da janela do console, você precisará ir para o domínio que está em casa aos servidores front-ends do seu Skype for Business Server e expandir as zonas de **pesquisa direta** .
    
4. Verifique quais das opções abaixo você tem:
    
   - Qualquer registro de host A ou AAAA para seu servidor front-end (padrão ou empresarial) ou pools front-ends.
    
   - Qualquer registro de host A ou AAAA para um director ou um pool de diretor (uma configuração opcional que você pode ter na sua implantação).
    
5. Depois disso, clique com o botão direito do mouse no nome do domínio SIP e escolha **Novo Alias (CNAME)** no menu.
    
6. Na caixa de texto **Nome de alias**, digite lyncdiscoverinternal como nome do host para a URL interna do serviço de Descoberta Automática.
    
7. No **nome de domínio totalmente qualificado (FQDN para host de destino**, você precisará digitar ou navegar até o FQDN dos serviços Web internos do seu pool de front-end (ou servidor de front-end único ou diretor ou diretor), identificado na etapa 4 acima. Clique em OK depois de inseri-lo.
    
8. Você precisará criar um novo registro CNAME de descoberta automática na zona de pesquisa direta para cada domínio SIP com suporte no ambiente do Skype for Business Server.
    
### <a name="create-an-external-dns-cname-record"></a>Criar um registro CNAME de DNS externo

1. As etapas aqui apresentadas são genéricas, pois não sabemos qual provedor DNS público você usará, mas vamos ajudá-lo mesmo assim. Faça logon no provedor DNS público com uma conta que aceite a criação de novos registros DNS.
    
2. Nesse momento, um domínio SIP já deve existir para o Skype for Business Server. Expanda ou abra a **Zona de Pesquisa Direta** desse domínio SIP.
    
3. Verifique quais das opções abaixo você tem:
    
   - Qualquer registro de host A ou AAAA para seu servidor front-end (padrão ou empresarial) ou pools front-ends.
    
   - Qualquer registro de host A ou AAAA para um director ou um pool de diretor (uma configuração opcional que você pode ter na sua implantação).
    
4. Depois de obter essas informações, você poderá selecionar uma opção para criar um **Novo Alias (CNAME)**.
    
5. Agora digite um **Nome de Alias**. Você deve digitar lyncdiscover aqui para a URL externa de serviço de Descoberta Automática.
    
6. Em seguida, deve haver uma área para inserir um **FQDN para host de destino**, que precisa ser o FQDN do seu pool de front-end (ou servidor front-end único ou diretor ou diretor), identificado na etapa 3 acima.
    
7. Talvez seja necessário salvar aqui, ou se você precisar criar registros CNAME adicionais na zona de pesquisa direta de cada domínio SIP em seu ambiente do Skype for Business Server, você deverá fazer isso, mas quando estiver pronto, salve o seu trabalho.
    
### <a name="create-an-internal-dns-a-record"></a>Criar registro A de DNS interno

1. Faça logon em um servidor DNS em uma rede que seja membro do grupo **Admins. do Domínio** ou do grupo **DnsAdmins**.
    
2. Clique em **Iniciar**, escolha **Ferramentas Administrativas** (talvez você precise **Pesquisar**, se ela for uma opção fora do menu Iniciar) e clique em **DNS** para abrir o snap-in administrativo do DNS.
    
3. No painel à esquerda da janela do console, você precisará ir para o domínio que está em casa aos servidores front-ends do seu Skype for Business Server e expandir as zonas de **pesquisa direta** .
    
4. Verifique quais das opções abaixo você tem:
    
   - Qualquer registro de host A ou AAAA para seu servidor front-end (padrão ou empresarial) ou pools front-ends.
    
   - Qualquer registro de host A ou AAAA para um director ou um pool de diretor (uma configuração opcional que você pode ter na sua implantação).
    
5. Depois disso, clique com o botão direito do mouse no nome do domínio SIP e escolha **Novo Host (A ou AAAA)** no menu.
    
6. Na caixa de texto **Nome**, digite lyncdiscoverinternal como nome do host para a URL interna do serviço de Descoberta Automática.
    
7. Na caixa de texto **endereço IP** , digite o endereço IP dos serviços Web internos para seu pool de front-end (ou servidor de front-end único ou diretor ou diretor), identificado na etapa 4 acima.
    
8. Ao concluir esse procedimento, clique em **Adicionar Host** e clique **OK**.
    
9. Você precisará criar um novo registro de descoberta automática A ou AAAA na zona de pesquisa direta para cada domínio SIP com suporte no ambiente do Skype for Business Server. Para isso, repita as etapas de 6 a 8 quantas vezes forem necessárias.
    
10. Ao terminar, clique em **Concluído**.
    
### <a name="create-an-external-dns-a-record"></a>Criar um registro A de DNS externo

1. As etapas aqui apresentadas são genéricas, pois não sabemos qual provedor DNS público você usará, mas vamos ajudá-lo mesmo assim. Faça logon no provedor DNS público com uma conta que aceite a criação de novos registros DNS.
    
2. Nesse momento, um domínio SIP já deve existir para o Skype for Business Server. Expanda ou abra a **Zona de Pesquisa Direta** desse domínio SIP.
    
3. Verifique quais das opções abaixo você tem:
    
   - Qualquer registro de host A ou AAAA para seu servidor front-end (padrão ou empresarial) ou pools front-ends.
    
   - Qualquer registro de host A ou AAAA para um director ou um pool de diretor (uma configuração opcional que você pode ter na sua implantação).
    
4. Depois de obter essas informações, você poderá selecionar uma opção para criar um **Novo Host A ou AAAA**.
    
5. Agora digite um **Nome**. Você deve digitar lyncdiscover aqui para a URL externa de serviço de Descoberta Automática.
    
6. Em seguida, deve haver uma área para inserir um **endereço IP**, que deverá ser o IP do seu pool Front-end (ou servidor front-end único ou diretor ou diretor), identificado na etapa 3 acima.
    
7. Talvez seja necessário salvar aqui, ou se você precisar criar registros adicionais A ou AAAA na zona de pesquisa direta de cada domínio SIP para o seu ambiente do Skype for Business Server, você deve fazer isso, mas quando estiver pronto, salve o seu trabalho.
    
## <a name="modify-certificates"></a>Modificar certificados
<a name="ModCerts"> </a>

Se você tiver dúvidas sobre o planejamento de certificados, documentamos isso em nosso artigo nosso [plano de mobilidade para o Skype for Business Server](../plan-your-deployment/mobility.md) . Depois de você ler esse artigo, continuaremos com as seguintes etapas:
  
- Preciso de novos certificados?
    
- Solicitando novos certificados à AC (Autoridade de Certificação).
    
- Atualizando certificados in-loco por meio de substituições com o PowerShell.
    
- Verificar os certificados usando o snap-in de certificados no console de gerenciamento Microsoft (MMC).
    
### <a name="do-i-need-new-certificates"></a>Preciso de novos certificados?

1. Primeiro, talvez seja necessário verificar e ver quais certificados estão no local e se eles têm ou não as entradas de que você precisa. Para fazer isso, você precisará conectar-se ao seu servidor do Skype for Business com uma conta de administrador local. Essa conta também pode precisar ter direitos à CA (autoridade de certificação) de emissão, para algumas dessas etapas.
    
2. Abrir o Shell de gerenciamento do Skype for Business Server (você pode usar a pesquisa para localizá-lo se não o tiver fixado no menu iniciar ou na barra de tarefas).
    
3. Você precisa saber quais certificados foram atribuídos antes de tentar adicionar um certificado atualizado. Portanto, no comando, digite:
    
   ```
   Get-CsCertificate
   ```

4. As informações da Etapa 3 serão exclusivas para você. É necessário verificar se você tem um certificado único atribuído a vários componentes ou se você tem um certificado para cada componente. O parâmetro **Use** informará como o certificado está sendo usado, e o parâmetro **Thumbprint** informará se todos são o mesmo certificado ou se são vários certificados.
    
5. Se você tiver as entradas SAN recomendadas na seção de planejamento, você está no caminho certo. Caso contrário, deverá solicitar um novo certificado ou vários certificados (dependendo de sua configuração) à Autoridade de Certificação.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Solicitar um novo certificado ou certificados à AC

1. Depois de verificar quais entradas SAN possui, você constata que tem um **certificado único** (depois de fazer a verificação seguindo as etapas mencionadas acima) e que não tem todas as entradas necessárias. Você deve fazer uma nova solicitação de certificado à AC. Abra seu PowerShell do Skype for Business Server:
    
   - Para um SAN de Serviço de Descoberta Automática ausente (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Agora, se você tiver vários domínios SIP, não será possível usar o parâmetro AllSipDomain como no exemplo acima. Em vez disso, use o parâmetro DomainName. Quando você usar o parâmetro DomainName, deverá definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover. Um exemplo seria (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Ou, depois de verificar quais entradas SAN possui, você constata que tem **vários certificados** que não possuem todas as entradas necessárias. Você deverá solicitar um novo certificado à AC. Abra seu PowerShell do Skype for Business Server:
    
   - Para um SAN de Serviço de Descoberta Automática ausente (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Agora, se você tiver vários domínios SIP, não será possível usar o parâmetro AllSipDomain como no exemplo acima. Em vez disso, use o parâmetro DomainName. Quando você usar o parâmetro DomainName, deverá definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover. Exemplos seriam (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Depois que os novos certificados forem gerados pela AC, você deverá atribuí-los.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Atribuir certificados usando o Shell de Gerenciamento do Skype for Business Server

- Dependendo da resposta obtida na seção "Preciso de novas certificações?", você deverá executar **um** dos seguintes comandos.
    
  - Se você tiver um certificado único para tudo (as impressões digitais são idênticas), execute o seguinte:
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Se você tiver diferentes certificados para diferentes funções (as impressões digitais são diferentes), execute o seguinte:
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Exibindo certificados no MMC (Console de Gerenciamento Microsoft)

1. Você pode consultar seus certificados usando o snap-in de certificados do MMC. Basta digitar MMC no campo de pesquisa e ele será exibido como uma opção do aplicativo.
    
2. Para adicionar o snap-in de certificados, clique em **Arquivo** e em **Adicionar/Remover Snap-In...** (ou use o atalho do teclado **Ctrl+M**). A opção **Certificados** aparecerá no painel esquerdo, selecione-a, selecione **Conta de Computador** na janela pop-up e clique em **Avançar**.
    
3. Ainda na janela pop-up, se você estiver usando o computador onde estão os certificados que deseja consultar, mantenha a seleção **Computador Local**. Se estiver trabalhando em um computador remoto, altere o botão de opção para **Outro Computador** e insira o FQDN do computador ou use o botão **Procurar** para procurar esse computador por meio do AD. Depois de selecionar o computador, você precisará clicar em **concluir** quando estiver pronto e em **OK** para adicionar o snap-in ao MMC.
    
4. Expanda a seção **certificados** no painel esquerdo do MMC. Expanda também a pasta **Pessoal** e selecione **Certificados**. Isso permite que você veja os certificados nesse repositório.
    
5. Você deve localizar o certificado que deseja exibir, clicar com o botão direito do mouse nele e selecionar **Abrir**.
    
    > [!NOTE]
    > Como saber qual é o certificado? Ele deve ser o único certificado atribuído a tudo para o seu farm, ou você pode ter vários certificados para itens diferentes, como os serviços Web internos padrão, etc., e, nesse caso, talvez seja necessário examinar vários certificados. Vários certificados terão a mesma impressão digital. 
  
6. No modo de exibição **Certificado**, selecione **Detalhes**. Isso permitirá que você veja o nome do requerente do certificado quando selecionar **Entidade**, bem como o nome da entidade atribuída e as propriedades associadas.
    
7. Você também deverá verificar as entradas de **Nome Alternativo da Entidade**. Você encontrará uma ou mais das opções a seguir:
    
   - O nome do pool para este pool ou o nome do servidor único se não for um pool.
    
   - O nome do servidor ao qual o certificado está atribuído.
    
   - Registros de URL Simples, normalmente reunir e discar.
    
   - Serviços Web internos e serviços Web nomes externos (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas opções feitas no construtor de topologias e nas seleções de serviços Web do ridden.
    
   - Se já foi atribuído, o lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<registros\> sipdomain.
    
     Você deverá verificar vários certificados, se tiver mais de um atribuído (consulte a Observação anterior).
    
8. Portanto, se você encontrar o lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros, você já tem isso configurado. Você pode fechar o MMC.
    
9. Se eles não estiverem atribuídos, você deverá fazer uma nova solicitação de certificado (como descrito anteriormente) ou instalá-los após a solicitação (recomendamos usar o PowerShell mencionado anteriormente).
    
## <a name="configure-the-reverse-proxy"></a>Configurar o proxy inverso
<a name="ConfigRP"> </a>

As etapas a seguir não precisam ser seguidas à risca. Nas versões anteriores do produto, explicamos, por exemplo, a configuração do TMG (Threat Management Gateway) e, caso você não esteja usando esse recurso, deverá usar essas etapas adaptando-as para sua própria versão.
  
A TMG não está mais sendo oferecida pela Microsoft como um produto e, se você ainda precisar configurá-lo, poderá ver as [etapas do Lync Server 2013](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx). Mas as informações a seguir devem ser mais úteis, mesmo se não houver nenhuma maneira de fornecer etapas específicas passo a passo para cada proxy reverso.
  
Devemos ter em mente duas considerações importantes:
  
- Você fará sua solicitação inicial de Descoberta Automática por HTTPS (recomendável)?
    
  - Se você tiver uma regra de publicação na Web, deverá modificá-la.
    
  - Se você ainda não tiver uma regra de publicação na Web, deverá criá-la.
    
- Se você estiver fazendo sua solicitação inicial de Descoberta Automática por HTTP, também deverá criar ou modificar essa regra.
    
> [!NOTE]
> **Importante** Um valor de tempo limite de proxy é um número que varia de implantação para implantação. Você deve monitorar a implantação e modificar o valor da melhor experiência para os clientes. Talvez seja possível definir o valor tão baixo quanto 200. Se você estiver oferecendo suporte a clientes móveis do Lync em seu ambiente, você deve definir o valor para 960 para permitir o tempo limite de notificações por push do Office 365, que têm um valor de tempo limite de 900. É muito provável que você precise aumentar o valor de tempo limite para evitar que o cliente se desconecte quando o valor for muito baixo ou diminuir o número se as conexões pelo proxy não forem desconectadas, mas muito demoradas após o cliente ter sido desconectado. O monitoramento e a criação de uma função de determinação do que é normal para o seu ambiente é a única maneira precisa de determinar a configuração apropriada para esse valor.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificar a regra de publicação na Web existente para SAN e URL externa de Descoberta Automática

1. Abra a interface de proxy reverso.
    
2. Você precisará localizar sua regra de publicação na Web e escolher a opção de edição (ela pode estar em um menu ou uma guia, dependendo da configuração de proxy reverso).
    
3. Deve haver uma área que informa o que esta regra de publicação da Web é aplicada. Você deve modificar essa regra para sites de entrada ou para solicitações a sites. Você **adicionará** uma nova entrada.
    
4. Digite o nome do seu site de descoberta automática (o exemplo que usaremos é lyncdiscover.contoso.com) e clique em **OK** ou **salvar**, dependendo do formato do seu proxy reverso.
    
5. Você pode ter um novo certificado que contenha a entrada SAN de Descoberta Automática. Isso também precisa ser instalado e configurado para uso de acordo com as configurações do seu proxy reverso. Salve tudo após concluir a configuração.
    
6. Se o seu proxy reverso tiver uma funcionalidade de **teste** , use-o para garantir que tudo esteja funcionando corretamente.
    
7. Agora, talvez seja necessário repetir essas etapas se você tiver um diretor ou um pool de directors em seu ambiente (isso significa que você tem uma segunda regra).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Criar uma regra de publicação na Web para a URL externa de descoberta automática

1. Abra a interface de proxy reverso.
    
2. Você precisará localizar onde a interface você cria suas regras de publicação na Web e escolher a opção **nova** ou **criar** (ela pode estar em um menu ou uma guia, dependendo da configuração de proxy reverso). Você está procurando a opção para criar uma nova regra de publicação na Web.
    
3. Normalmente, você deverá inserir as seguintes informações:
    
   - **Nome**: o nome da regra
    
   - **Ação da regra**: nesse caso, é uma regra de **permissão** , você está permitindo que um passe pelo seu proxy reverso.
    
   - A regra **Publicação** ou opção que você está escolhendo seria **único site da Web ou equilibrador de carga**.
    
   - Para acesso externo, deve ser **SSL**, escolha essa opção.
    
   - Você precisará publicar um caminho para **publicação interna**e inserir o FQDN dos serviços Web externos no balanceador de carga do pool de front-end (ou o FQDN do balanceador de carga do pool do diretor, se tiver um), um exemplo seria sfb_ pool01. contoso. local.
    
   - Você deve digitar ** / *** como o caminho a ser publicado, mas também precisa encaminhar **o cabeçalho original do host**.
    
   - Haverá uma opção para os detalhes ou informações do **nome público ou externo**. Este é o local onde você poderá inseri-los:
    
   - **Aceitar solicitações**, mas deve ser para o nome do domínio.
    
   - Para o **Nome**, você deve inserir **lyncdiscover.** <sipdomain>(esta é a URL do serviço de descoberta automática externa). Agora, se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, será necessário digitar o FQDN dos serviços Web externos em seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).
    
   - Haverá uma opção de **caminho** , e você precisará digitar ** / *** aqui.
    
   - Você deverá selecionar um **Ouvinte SSL** com o certificado público atualizado.
    
   - 
            A opção **Delegação de Autenticação** deve ser definida como **Sem delegação**, mas a autenticação direta de cliente **deve** ser permitida.
    
   - A regra deve ser definida para **Todos os usuários**.
    
   - Essa deve ser toda a informação que você precisa para criar esta regra e permitir que você continue.
    
4. Você deve garantir que o **cabeçalho do host original** seja encaminhado.
    
5. As portas do **Web Server** também deverão ser definidas. Para isso, faça o seguinte:
    
   - **Redirecione as solicitações para a porta HTTP** e o número da porta deverá ser **8080**.
    
   - **Redirecione as solicitações para a porta SSL** e o número da porta deverá ser **4443**.
    
6. Quando tudo estiver configurado, você deverá salvar ou aplicar a configuração e depois testar a regra.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Para criar uma regra de publicação Web para a porta 80 (opcional)

1. Abra a interface de proxy reverso.
    
2. Você precisará localizar onde a interface você cria suas regras de publicação na Web e escolher a opção **nova** ou **criar** (ela pode estar em um menu ou uma guia, dependendo da configuração de proxy reverso). Você está procurando a opção para criar uma nova regra de publicação na Web.
    
3. Normalmente, você deverá inserir as seguintes informações:
    
   - **Nome**: o nome da regra
    
   - **Ação da regra**: nesse caso, é uma regra de **permissão** , você está permitindo que um passe pelo seu proxy reverso.
    
   - A regra **Publicação** ou opção que você está escolhendo seria **único site da Web ou equilibrador de carga**.
    
   - Esta deve ser uma **conexão não segura para conectar-se à farm de servidores ou ao servidor Web publicado**.
    
   - Você precisará publicar um caminho para **publicação interna**e digitar o FQDN do **endereço VIP** do balanceador de carga do pool de front-end, um exemplo seria sfb_pool01. contoso. local.
    
   - Você deve digitar ** / *** como o caminho a ser publicado, mas também precisa encaminhar **o cabeçalho original do host**.
    
   - Haverá uma opção para os detalhes ou informações do **nome público ou externo**. Este é o local onde você poderá inseri-los:
    
   - **Aceitar solicitações**, mas deve ser para o nome do domínio.
    
   - Para o **Nome**, você deve inserir **lyncdiscover.** <sipdomain>(esta é a URL do serviço de descoberta automática externa).
    
   - Haverá uma opção de **caminho** , e você precisará digitar ** / *** aqui.
    
   - Você precisará selecionar um ouvinte da Web ou permitir que seu proxy inverso crie um para você.
    
   - 
            A opção **Delegação de Autenticação** deve ser definida como **Sem delegação**, mas a autenticação direta de cliente **não deve** ser permitida.
    
   - A regra deve ser definida para **Todos os usuários**.
    
   - Essa deve ser toda a informação que você precisa para criar esta regra e permitir que você continue.
    
4. As portas do **Web Server** deverão ser definidas. Para isso, faça o seguinte:
    
   - **Redirecione as solicitações para a porta HTTP** e o número da porta deverá ser **8080**.
    
   - **Redirecione as solicitações para a porta SSL** e o número da porta deverá ser **4443**.
    
5. Quando tudo estiver configurado, você deverá salvar ou aplicar a configuração e depois testar a regra.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurar Descoberta Automática para Mobilidade com implantações híbridas
<a name="ConfigAutoD"> </a>

Ambientes híbridos no Skype for Business Server são ambientes que combinam um ambiente local e do O365. Quando o Skype for Business Server está funcionando em um ambiente híbrido, o serviço de descoberta automática precisa ser capaz de localizar um usuário a partir de qualquer um desses ambientes.
  
Para permitir que os clientes móveis descubram onde um usuário está localizado, o serviço de Descoberta Automática deve ser configurado com uma nova URL. As etapas são as seguintes:
  
1. Abrir o Shell de gerenciamento do Skype for Business Server.
    
2. Execute o seguinte para obter o valor do atributo **ProxyFQDN** para o seu ambiente do Skype for Business Server:
    
   ```
   Get-CsHostingProvider
   ```

3. Então, na janela do Shell, excute:
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Onde [identidade] é substituído pelo nome do domínio do espaço de endereço SIP compartilhado.
    
## <a name="test-your-mobility-deployment"></a>Testar a implantação de mobilidade
<a name="TestMobility"> </a>

Depois de implantar o serviço de mobilidade do Skype for Business Server e o serviço de descoberta automática do Skype for Business Server, você desejará executar uma transação de teste para garantir que a sua implantação esteja funcionando corretamente. Você pode executar **Test-CsUcwaConference** para testar a capacidade de dois usuários de criar, ingressar e se comunicar em uma conferência. Você precisará de dois usuários (reais ou de teste) e de suas respectivas credenciais completas para executar esse teste. Esse comando funciona para clientes do Skype for Business e para clientes do Lync Server 2013.
  
Para clientes do Lync Server 2010 no Skype for Business Server 2015, você precisará executar **Test-CsMcxP2PIM** para testar. Os usuários do Lync Server 2010 ainda precisarão de usuários reais ou usuários de teste predefinidos e você precisará das credenciais da senha.

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Testar a conferência para clientes móveis do Skype for Business e do Lync 2013

1. Faça logon como membro da função **CsAdministrator** em qualquer computador em que o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estejam instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server** (você pode digitar o nome na pesquisa ou vá para **todos os programas** e escolha-o).
    
3. Na linha de comando, digite:
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Também é possível definir as credenciais em um script e enviá-las para o cmdlet de teste. Temos um exemplo disso a seguir.
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Testar a conferência para clientes móveis do Lync 2010

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.

1. Faça logon como membro da função **CsAdministrator** em qualquer computador em que o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estejam instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server** (você pode digitar o nome na pesquisa ou vá para **todos os programas** e escolha-o).
    
3. Na linha de comando, digite:
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Também é possível definir as credenciais em um script e enviá-las para o cmdlet de teste. Temos um exemplo disso a seguir.
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Para examinar melhor os procedimentos de comando, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurar para notificações por push
<a name="ConfigPush"> </a>

As notificações por push, na forma de notificações, ícones ou alertas, podem ser enviadas para um dispositivo móvel mesmo quando o aplicativo Skype ou Lync está inativo. Mas o que são as notificações por push? Elas são alertas de evento, como um convite novo ou perdido enviado por mensagem instantânea ou uma mensagem de voz recebida. O serviço Skype for Business Server Mobility envia essas notificações para o serviço de notificação por push do Skype for Business Server baseado em nuvem, que envia as notificações para o serviço de notificação por push da Microsoft (MSNS) para usuários do Windows Phone.
  
Esta funcionalidade não é alterada no Lync Server 2013, mas se você tiver um servidor do Skype for Business, você desejará fazer o seguinte:
  
- Para um servidor de borda do Skype for Business Server, adicione um novo provedor de hospedagem, o Microsoft Skype for Business Online, e configure a Federação do provedor de hospedagem entre a sua organização e o Skype for Business online.
    
- Habilite notificações por push executando o cmdlet **Set-CsPushNotificationConfiguration**. Por padrão, as notificações por push estão desativadas.
    
- Teste sua configuração de federação e as notificações por push.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurar o Servidor de Borda do Skype for Business para notificações por push

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador no qual o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Adicionar um provedor de hospedagem online do Skype for Business Server.
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Por exemplo:
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Não é possível ter mais de um relacionamento de federação com um único provedor de host. Ou seja, se você já tiver configurado um provedor de host que tenha um relacionamento de federação com sipfed.online.lync.com, não adicione outro provedor de host a ele, mesmo se a identidade do provedor de host for diferente de SkypeOnline. 
  
4. Configurar a Federação do provedor de hospedagem entre sua organização e o serviço de notificação por push no Skype for Business online. Na linha de comando, digite:
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Habilitar notificações por push

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador no qual o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Habilite notificações por push:
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Habilite a federação:
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Testar a federação e as notificações por push

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador no qual o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Teste a configuração da federação:
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Por exemplo:
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Teste as notificações por push:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Por exemplo:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Configurar a política de mobilidade
<a name="ConfigMob"> </a>

Você tem a capacidade do Skype for Business Server para determinar quem pode usar seu serviço de mobilidade, ligar pelo trabalho, voz sobre IP (VoIP) ou vídeo, bem como se o WiFi será necessário para VoIP ou vídeo. O recurso Telefonar via Trabalho permite que um usuário móvel use o número de seu telefone comercial, em vez de seu número particular, para fazer e receber chamadas. A pessoa na outra extremidade da linha não vê o número do celular desse usuário móvel, o que permite que o usuário móvel evite cobranças de chamadas de saída. Quando VoIP e vídeo são configurados, os usuários podem receber e fazer chamadas VoIP e de vídeo. As configurações para o uso de WiFi determinam se o dispositivo móvel de um usuário precisa usar WiFi através de uma rede de dados de celular.
  
Mobilidade, chamada por meio de trabalho, e os recursos de VoIP e vídeo são habilitados por padrão. As configurações para exigir WiFi para VoIP e vídeo estão desabilitadas. Um administrador pode alterar essas configurações em nível global, por site ou por usuário.
  
Para poder usar os recursos de mobilidade e ligar pelo trabalho, os usuários precisam estar:
  
- Habilitado para o Skype for Business Server
    
- Estar habilitados para Enterprise Voice.
    
- Foi atribuída uma política de mobilidade com a opção **EnableMobility** definida como **true**.
    
Para usar o recurso Telefonar via Trabalho, os usuários devem:
  
- Ter uma política de voz atribuída com a opção **Habilitar toques de telefones simultâneos** selecionada.
    
- Atribuída uma política de mobilidade com o **EnableOutsideVoice** definido como **true**.
    
> [!NOTE]
> Usuários não habilitados para Enterprise Voice podem usar seus dispositivos móveis para fazer chamadas VoIP de Skype para Skype ou podem ingressar em conferências usando o link Clique para Ingressar quando estiverem usando dispositivos móveis, se as opções apropriadas estiverem definidas para a política de voz correspondente. Há mais detalhes no tópico PLANEJAMENTO. 
  
### <a name="modify-global-mobility-policy"></a>Modificar a política global de mobilidade

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador no qual o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Desative o acesso à mobilidade e faça chamadas por meio do trabalho global, digitando:
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Você pode desativar a chamada por meio de trabalho sem desativar o acesso à mobilidade. Mas você não pode desativar o Mobility sem também desativar a chamada por meio do trabalho. 
  
    Para obter mais informações, consulte [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modificar política de mobilidade por site

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador no qual o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Você pode criar uma política no nível de site, desativar VoIP e vídeo, habilitar Exigir WiFi para Áudio IP e Exigir WiFi para Vídeo IP por site. Digite:
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Saiba mais em [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modificar política de mobilidade por usuário

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador no qual o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Crie políticas de mobilidade em nível de usuário e desative a mobilidade e a chamada por meio do trabalho por usuário. Digite:
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Mais um exemplo:
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Você pode desativar a chamada por meio de trabalho sem desativar o acesso à mobilidade. Mas você não pode desativar o Mobility sem também desativar a chamada por meio do trabalho. 
  

