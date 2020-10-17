---
title: 'Lync Server 2013: configurar regras de publicação na Web para um único pool interno'
description: 'Lync Server 2013: configurar regras de publicação na Web para um único pool interno.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45015c90fdac92fb488affc871f2cfaf9d7506a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560507"
---
# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>Configurar regras de publicação na Web para um único pool interno no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-07-07_

O Microsoft Forefront Threat Management Gateway 2010 e o roteamento de solicitações de aplicativos do Internet Information Server (IIS ARR) usam regras de publicação na Web para publicar recursos internos, como uma URL de reunião, para os usuários na Internet.

Além das URLs de serviços Web para os diretórios virtuais, você também deve criar regras de publicação para URLs simples, a URL do LyncDiscover e o servidor do Office Web Apps. Para cada URL simples, é necessário criar uma regra individual no proxy inverso que aponta para essa URL simples.

Se você implantar a versão móvel e usar a descoberta automática, é necessário criar uma regra de publicação para a URL do Serviço de Descoberta Automática externo. A descoberta automática também requer regras de publicação para a URL externa dos serviços Web do Lync Server para seu pool de diretores e pool de front-ends. Para obter detalhes sobre como criar as regras de publicação na Web para descoberta automática, consulte [Configurando o proxy reverso para mobilidade no Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Use os procedimentos a seguir para criar regras de publicação da Web.

<div>


> [!NOTE]  
> Estes procedimentos presumem que você tenha instalado a edição Standard do Forefront Threat Management Gateway (TMG) 2010 ou tenha instalado e configurado o Internet Information Server com a extensão de roteamento de solicitação de aplicativo (IIS ARR). Você usa a TMG ou a ARR do IIS.



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>Para criar uma regra de publicação de servidor Web no computador que está executando o TMG 2010

1.  Clique em **Iniciar**, selecione **Programas**, selecione **Microsoft Forefront TMG** e clique em **Gerenciamento de forefront TMG**.

2.  No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **Política de firewall**, selecione **Novo** e clique em **Regra de publicação de site**.

3.  Na página **Bem-vindo à Nova Regra de Publicação da Web**, digite um nome de exibição para a regra de publicação (por exemplo, LyncServerWebDownloadsRule).

4.  Na página **Selecionar Ação da Regra**, selecione **Permitir**.

5.  Na página **Tipo de Publicação**, selecione **Publicar um único site ou um balanceador de carga na Web** e clique em Avançar.

6.  Na página **Segurança da Conexão do Servidor**, selecione **Usar SSL para conectar ao servidor da Web publicado ou ao farm de servidores**.

7.  Na página **Detalhes de Publicação Interna**, digite o FQDN (nome de domínio totalmente qualificado) da Web farm interna que hospeda o conteúdo das reuniões e o conteúdo do Catálogo de Endereços na caixa **Nome do site interno**.
    
    <div>
    

    > [!NOTE]  
    > Se o seu servidor interno é um servidor Standard Edition, este FQDN é o FQDN do servidor Standard Edition. Se seu servidor interno é um pool de Front-Ends, este FQDN é um IP virtual (VIP) de balanceador de carga de hardware que equilibra a carga dos servidores de farm da web internos. O servidor TMG deve ser capaz de resolver o FQDN ao endereço IP do servidor web interno. Se o servidor TMG não puder resolver o FQDN para o endereço IP correto, você poderá selecionar <STRONG>usar um nome de computador ou endereço IP para se conectar ao servidor publicado</STRONG>e, em seguida, na caixa <STRONG>nome do computador ou</STRONG> <STRONG>endereço IP</STRONG> , digite o endereço IP do servidor Web interno. Se você fizer isso, você deve verificar se a porta 53 é aberta no servidor TMG e se ela pode acessar um servidor DNS que reside na rede de perímetro. Também  pode usar as entradas no arquivo de hosts local para fornecer uma resolução de nome.

    
    </div>

8.  Na página **detalhes de publicação interna** , na caixa **caminho (opcional)** , digite **/\*** como o caminho da pasta a ser publicada.
    
    <div>
    

    > [!NOTE]  
    > No assistente de publicação de site, só é possível especificar um caminho. Caminhos adicionais podem ser adicionados modificando as propriedades da regra.

    
    </div>

9.  Na página **Detalhes do Nome Público**, confirme se   **Este nome de domínio ** está selecionado para **Aceitar Solicitações de**, digite o FQDN dos serviços Web externos na caixa **Nome Público**.

10. Na página **Selecionar Ouvinte da Web**, clique em **Novo** para abror o Assistente para Definição de Novo Ouvinte da Web.

11. Na página **Bem-vindo ao Assistente de Novo Ouvinte da Web**, digite um nome para o ouvinte da Web na caixa **Nome do ouvinte da Web** (por exemplo, LyncServerWebServers) e clique em Avançar.

12. Na página **Segurança da Conexão do Cliente**, selecione **Exigir conexões SSL seguras com clientes**.

13. Na página **Endereços IP do Ouvinte da Web**, selecione **Externo** e clique em **Selecionar Endereços IP**.

14. Na página **Seleção do IP do Ouvinte Externo**, selecione **Endereços IP especificados no computador do Forefront TMG da rede selecionada**, selecione o endereço IP apropriado e clique em **Adicionar**.

15. Na página **Certificados SSL de Ouvinte**, selecione **Atribuir um certificado para cada endereço IP**, selecione o endereço IP que está associado ao FQDN da Web externo e clique em **Selecionar Certificado**.

16. Na página **Selecionar Certificado**, selecione o certificado que corresponde ao nome público especificado na etapa 9 e clique em **Selecionar**.

17. Na página **Configuração da Autenticação**, selecione **Sem Autenticação**.

18. Na página **Configurações de Logon Único**, clique em **Avançar**.

19. Na página **Concluindo o Assistente de Novo Ouvinte da Web**, verifique se as configurações de **Ouvinte da Web** estão corretas e clique em **Concluir**.

20. Na página **Delegação de autenticação**, selecione **Nenhuma delegação, mas o cliente pode autenticar diretamente**.

21. Na página **Conjunto de Usuários**, clique em **Avançar**.

22. Na página **Concluir o novo assistente da regra de publicação da Web**, verifique se as configurações da regra de publicação da Web estão corretas e clique em **Finalizar**.

23. Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>Para criar uma regra de publicação de servidor Web no computador que executa o IIS ARR

1.  Vincule o certificado que você usará para o proxy reverso para o protocolo HTTPS. Clique em **Iniciar**, selecione **programas**, selecione **Ferramentas administrativas**e clique em **Gerenciador dos serviços de informações da Internet (IIS)**.
    
    <div>
    

    > [!NOTE]  
    > Ajuda adicional, capturas de tela e orientações sobre a implantação e configuração do IIS ARR podem ser encontradas no artigo NextHop <A href="https://go.microsoft.com/fwlink/?linkid=293391">usando o IIS arr como um proxy reverso para o Lync Server 2013</A>.

    
    </div>

2.  Se você ainda não tiver feito isso, importe o certificado que será usado para o proxy reverso. No **Gerenciador de serviços de informações da Internet (IIS)**, clique no nome do servidor proxy reverso no tamanho da esquerda do console. No meio do console em **IIS** , localize **certificados de servidor**. Clique com o botão direito do mouse em **certificados de servidor** e selecione **abrir recurso**.

3.  No lado direito do console, clique em **importar...**. Digite o caminho e o nome de arquivo do certificado com a extensão ou clique em **..** . para procurar o certificado. Selecione o certificado e clique em **abrir**. Forneça a senha usada para proteger a chave privada (se você tiver atribuído uma senha ao exportar o certificado e a chave privada). Clique em **OK**. Se a importação do certificado tiver sido bem-sucedida, o certificado aparecerá como uma entrada no meio do console como uma entrada em **certificados de servidor**.

4.  Atribua o certificado a ser usado por HTTPS. No lado esquerdo do console, selecione o **site da Web padrão** do servidor IIS. No lado direito, clique em **ligações..**.. Na caixa de diálogo **ligações do site** , clique em **Adicionar..**.. Na caixa de diálogo **Adicionar Associação de site** , em **tipo:**, selecione **https**. Selecionar https permitirá que você selecione o certificado a ser usado para https. Em **certificado SSL:**, selecione o certificado que você importou para o proxy reverso. Clique em **OK**. Em seguida, clique em **fechar**. O certificado agora está ligado ao proxy reverso para SSL (Secure Socket Layer) e TLS (Transport Layer Security).
    
    <div>
    

    > [!IMPORTANT]  
    > Se você receber um aviso ao fechar as caixas de diálogo de vinculação que os certificados intermediários estão ausentes, será necessário localizar e importar o certificado de autoridade raiz da autoridade de certificação pública e quaisquer certificados de autoridade de certificação intermediários. Consulte as instruções na AC pública para a qual você solicitou o certificado e siga as instruções para solicitar e importar uma cadeia de certificados. Se você exportou o certificado do seu servidor de borda, é possível exportar o certificado de autoridade de certificação raiz e todos os certificados de autoridade de certificação intermediários associados ao servidor de borda. Importe o certificado de autoridade de certificação raiz para o computador (não deve ser confundido com o repositório do usuário) armazenamento de autoridades de certificação raiz confiáveis e certificados intermediários no repositório de autoridades de certificação intermediários do computador.

    
    </div>

5.  No lado esquerdo do console abaixo do nome do servidor IIS, clique com o botão direito do mouse em **farms de servidores** e clique em **criar farm de servidores..**..
    
    <div>
    

    > [!NOTE]  
    > Se você não vir o nó <STRONG>farms de servidores</STRONG> , precisará instalar o roteamento de solicitação de aplicativo. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores de proxy reverso para o Lync Server 2013</A>.

    
    </div>
    
    Na caixa de diálogo **criar farm de servidores** no **nome do farm de servidores**, digite o nome a (pode ser um nome amigável para fins de identificação) para a primeira URL. Clique em **Avançar**.

6.  Na caixa de diálogo **Adicionar servidor** no **endereço do servidor**, digite o FQDN (nome de domínio totalmente qualificado) dos serviços Web externos no servidor front-end. Os nomes que serão usados aqui para fins de exemplo são os mesmos que são usados na seção de planejamento para o proxy reverso, [proxy de Resumo de certificado-reverso no Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md). Referindo-se ao planejamento de proxy reverso, digitamos o FQDN `webext.contoso.com` . Confirme se a caixa de seleção ao lado de **online** está selecionada. Clique em **Adicionar** para adicionar o servidor ao pool de servidores Web para essa configuração.
    
    <div>
    

    > [!WARNING]  
    > O Lync Server usa balanceadores de carga de hardware para o diretor de pool e servidores front-end para tráfego HTTP e HTTPS. Você só fornecerá um FQDN ao adicionar um servidor ao farm de servidores do ARR do IIS. O FQDN será o servidor front-end ou o diretor nas configurações de servidor sem pool ou o FQDN do balanceador de carga de hardware configurado para pools de servidores. O único método com suporte para o balanceamento de carga de tráfego HTTP e HTTPS é usar balanceadores de carga de hardware.

    
    </div>

7.  Na caixa de diálogo **Adicionar servidor** , clique em **Configurações avançadas..**.. Isso abre uma caixa de diálogo para definir o roteamento de solicitação de aplicativo para as solicitações para o FQDN configurado. O objetivo é redefinir qual porta será usada quando a solicitação for processada pelo IIS ARR.
    
    Por padrão, a porta HTTP de destino deve ser definida como 8080. Clique em próximo ao **httpPort atual 80** e defina o valor como **8080**. Clique em próximo ao **httpsPort atual 443** e defina o valor como **4443**. Deixe o parâmetro **Weight** em 100. Se necessário, você pode redefinir os pesos de uma determinada regra quando tiver estatísticas da linha de base. Clique em **concluir** para concluir esta parte da configuração da regra.

8.  Você pode ver uma caixa de diálogo reescrever regras que informa que o Gerenciador do IIS pode criar uma regra de regravação de URL para rotear todas as solicitações de entrada para o farm de servidores automaticamente. Clique em **Sim**. Você vai ajustar as regras manualmente, mas selecionar Sim define a configuração inicial..

9.  Clique no nome do farm de servidores que você acabou de criar. Em **farm de servidores** no modo de exibição de recursos do Gerenciador do IIS, clique duas vezes em **cache**. Desmarque **Habilitar cache de disco**. Clique em **aplicar** no lado direito.

10. Clique no nome do farm de servidores. Em **farm de servidores** no modo de exibição de recursos do Gerenciador do IIS, clique duas vezes em **proxy**. Na página Configurações de proxy, altere o valor de **tempo limite (segundos)** para um valor apropriado para sua implantação. Clique em **aplicar** para salvar a alteração.
    
    <div>
    

    > [!IMPORTANT]  
    > O valor de tempo limite do proxy é um número que varia de implantação para implantação. Você deve monitorar sua implantação e modificar o valor da melhor experiência para os clientes. É possível definir o valor como baixo como 200. Se você estiver dando suporte a clientes móveis do Lync em seu ambiente, você deve definir o valor como 960 para permitir o tempo limite de notificações por push do Office 365 que têm um valor de tempo limite de 900. É muito provável que você precise aumentar o valor de tempo limite para evitar que o cliente seja desconectado quando o valor for muito baixo ou diminuir o número se as conexões por meio do proxy não forem desconectadas e muito longas após o cliente ter sido desconectado. O monitoramento e o alinhamento básico o que é normal para o seu ambiente é a única maneira precisa de determinar onde a configuração correta é para esse valor.

    
    </div>

11. Clique no nome do farm de servidores. Em **farm de servidores** no modo de exibição de recursos do Gerenciador do IIS, clique duas vezes em **regras de roteamento**. Na caixa de diálogo regras de roteamento em roteamento, desmarque a caixa de seleção ao lado de habilitar descarregamento SSL. Se a capacidade de desmarcar a caixa de seleção não estiver disponível, marque a caixa de seleção **usar URL Rewrite para inspecionar solicitações de entrada**. Clique em **aplicar** para salvar as alterações.
    
    <div>
    

    > [!WARNING]  
    > Não há suporte para o descarregamento de SSL pelo proxy reverso.

    
    </div>

12. Repita as etapas 5-11 para cada URL que deve passar pelo proxy reverso. Uma lista comum seria a seguinte:
    
      - Serviços Web de servidor front-end externo: webext.contoso.com (já configurado pelo passo inicial)
    
      - Serviços Web do diretor externos para Diretor: webdirext.contoso.com (opcional se um diretor estiver implantado)
    
      - Reunião de URL simples: meet.contoso.com
    
      - Discagem de URL simples: dialin.contoso.com
    
      - URL de descoberta automática do Lync: lyncdiscover.contoso.com
    
      - URL do servidor do Office Web Apps: officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > A URL do servidor do Office Web Apps usará um endereço httpsPort diferente. Na etapa 7, você define o <STRONG>httpsPort</STRONG> como <STRONG>443</STRONG> e o <STRONG>httpPort</STRONG> como a porta <STRONG>80</STRONG>. Todas as outras definições de configuração são as mesmas.

        
        </div>

13. No lado esquerdo do console, clique no nome do servidor IIS. No meio do console, localize **regravação de URL** em **IIS**. Clique duas vezes em URL Rewrite para abrir a configuração de regras de regravação de URL. Você deve ver as regras de cada farm de servidores criado nas etapas anteriores. Caso contrário, confirme se você clicou no nome do **servidor IIS** imediatamente abaixo do nó da **página inicial** no console do Gerenciador do servidor de informações da Internet.

14. Na caixa de diálogo de **reconfiguração de URL** , usando webext.contoso.com como exemplo, o nome completo da regra conforme exibido é **arr \_ webext.contoso.com \_ LoadBalance \_ SSL**.
    
      - Clique duas vezes na regra para abrir a caixa de diálogo **Editar regra de entrada** .
    
      - Clique em **Adicionar...** na caixa de diálogo **condições** .
    
      - Na entrada **Adicionar condição** em **condição:** digite **{host http \_ }**. (Conforme você digita, uma caixa de diálogo é exibida, permitindo que você selecione a condição). em **verificar se a cadeia de caracteres de entrada:** Select **corresponde ao padrão**. No tipo de **entrada padrão** **\*** . O **caso de ignorar** deve ser selecionado. Clique em **OK**.
    
      - Role para baixo na caixa de diálogo **Editar regra de entrada** para localizar a caixa de diálogo de **ação** . **Tipo de ação:** deve ser definido como **rota para o farm de servidores**, **esquema:** definido como **https://**, **farm de servidores:** definido como a URL à qual essa regra se aplica. Para este exemplo, ele deve ser definido como **webext.contoso.com**. **Caminho:** está definido como **/{R: 0}**
    
      - Clique em **aplicar** para salvar as alterações. Clique em **voltar às regras** para retornar às regras de regravação de URL.

15. Repita o procedimento definido na etapa 14 para cada regra de regravação SSL que você definiu, uma por URL de farm de servidores.
    
    <div>
    

    > [!WARNING]  
    > Por padrão, as regras HTTP também são criadas e são indicadas pelo nome semelhante às regras SSL. Para o nosso exemplo atual, a regra HTTP seria nomeada <STRONG>ARR_webext. contoso. com _loadbalance</STRONG>. Nenhuma modificação é necessária para essas regras e elas podem ser ignoradas com segurança.

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>Para modificar as propriedades da regra de publicação na Web no TMG 2010

1.  Clique em **Iniciar**, aponte para **programas**, selecione **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.

2.  No painel esquerdo, expanda **Nome do Servidor** e clique em **Política de Firewall**.

3.  No painel de detalhes, clique com o botão direito do mouse na regra de publicação de servidor Web que você criou no procedimento anterior (por exemplo, LyncServerExternalRule) e clique em **Propriedades**.

4.  Na página **Propriedades**, clique na guia **De** e faça o seguinte:
    
      - Na lista **Esta regra aplica-se ao tráfego destas origens**, clique em **Qualquer Lugar** e clique em **Remover**.
    
      - Clique em **Adicionar**.
    
      - Em **Adicionar Entidades de Rede**, expanda **Redes**, clique em **Externa**, clique em **Adicionar** e, em seguida, clique em **Fechar**.

5.  Na guia **Para**, verifique se a caixa de seleção **Encaminhar o cabeçalho do host original em vez do real** está marcada.

6.  Na guia **Ponte**, marque a caixa de seleção **Redirecionar a solicitação para a porta SSL** e especifique a porta **4443**.

7.  Na guia **Nome Público**, adicione as URLs simples (por exemplo, meet.contoso.com e dialin.contoso.com).

8.  Clique em **Aplicar** para salvar as alterações e clique em **OK**.

9.  Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>Para modificar as propriedades da regra de publicação na Web no IIS ARR

1.  Clique em **Iniciar**, selecione **programas**, selecione **Ferramentas administrativas**e clique em **Gerenciador dos serviços de informações da Internet (IIS)**.

2.  No lado esquerdo do console, clique no nome do servidor IIS.

3.  No meio do console, localize **regravação de URL** em **IIS**. Clique duas vezes em URL Rewrite para abrir a configuração de regras de regravação de URL.

4.  Clique duas vezes na regra que você precisa modificar. Faça suas modificações, conforme necessário, em **URL de correspondência**, **condições**, **variáveis de servidor** ou **ação**.

5.  Clique em **aplicar** para confirmar suas alterações. Clique em **voltar às regras** para modificar outras regras ou feche o console do **Gerenciador do IIS** se tiver concluído as alterações.

</div>

</div>

<span> </span>

</div>

</div>

</div>

