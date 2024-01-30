# Stable Diffusion WebUi and Kohya Simple Installation Guide - Stable Diffusion WebUi ve Kohya Basit Kurulum Rehberi

In this project, we will explain the installation of the "AUTOMATIC1111 stable diffusion webui" project and the "Kohya" project, which work in harmony with each other.

Bu projede birbiriyle uyumlu şekilde çalışan "AUTOMATIC1111 stable diffusion webui" projesi ile "Kohya" projesinin kurulumunu anlatacağız.

# English Guide
### Anaconda Installation
Install Anaconda from the link below
https://www.anaconda.com/download


### Install Visual Studio C++ Libraries
https://visualstudio.microsoft.com/tr/downloads/

Download and install visual studio from this url.

"C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\VC\Tools\MSVC\14.37.32822\bin\Hostx64\x86\"
Add directory to the path section in your Windows environment variables.

(Note that cl.exe is included in the directory!)

If your version is different, search for the cl.exe file in the Microsoft Visual Studio directory and copy the directory where cl.exe is located in the resulting files and add it to the environment variables as a path.
To see if you have done the installation correctly, open cmd and type the "cl" command. If the returned output is present, it means that you have successfully installed cl.exe.


### Install ENV Files
Install all yml files in the /conda-envs/ folder in this project with the following commands in the conda prompt. Before entering these commands, make sure that you are in the /conda-envs/ directory on the anaconda prompt.

"conda env create -f kohya.yml"

"conda env create -f stddataset.yml"

"conda env create -f stdutd.yml"


### Kohya Installation
https://github.com/bmaltais/kohya_ss/releases/tag/v22.6.0

Download the kohya files from the link and extract them to the directory you will install. My advice is to create an ai folder in the C directory for all the installations in this guide.


"conda activate kohya"

Activate the kohya virtual environment on the anaconda prompt with the command.

Navigate to the directory where you unzipped Kohya.

While in the Kohya virtual environment, type setup.bat on the command line and run the command.

It will give you options while installing. Choose which you will install on your local computer and answer no to all remaining questions. In the FP16 or BF16 question, if your graphics card is sufficient, select FP16 and continue. Answer all to the last question and complete the installation. Actually, all these steps are the default installation settings.

To check whether the installation is successful, run the gui.bat file on the anaconda prompt in the kohya virtual environment.
If http://127.0.0.1:7860/ is live, it means it has been installed successfully.

If you are getting an error, in order to install the same versions as me, go to the venv\Scripts directory from the current directory and run the venv virtual environment with the kohya environment open with the activate command. Then, copy the utdrequirements.txt file in the kohya_ss-22.6.0-venv folder in this github project to the venv\Scripts folder, install the requirements with the "pip install -r requirements.txt" command and re-run the gui.bat file. This will help solve your problem. This way, you will have installed the same versions as me. Remember that your Cuda version and the Cuda versions in our library must be compatible with your graphics card.

If you are getting the Bitsandbytes error, you should install with the pip install bitsandbytes command while the venv environment is active.


### Stable Diffusion setup
https://github.com/AUTOMATIC1111/stable-diffusion-webui/releases/tag/v1.4.0

Download the Stable Diffusion files from the link and extract them to the directory you will install. My advice is to create an ai folder in the C directory for all the installations in this guide.


"conda activate stdutd"

Activate the stdutd virtual environment with the command.


Navigate to the directory where you unzipped Stable Diffusion.

While in the virtual environment, type setup.bat on the command line and run the command.

Open the webui-user.bat file with notepad and replace the set "COMMANDLINE_ARGS=" line with "set COMMANDLINE_ARGS=--xformers" and run the bat file on Anaconda Prompt with the virtual environment open.

Then it will start the installation itself.


If you have problems downloading the "v1-5-pruned-emaonly" model during installation, download the model from the "https://huggingface.co/runwayml/stable-diffusion-v1-5/blob/main/v1-5-pruned-emaonly.safetensors" link. Download and install it in the "models\Stable-diffusion" folder and restart the installation. The problem will be solved.

If http://127.0.0.1:7860/ is live, it means it has been installed successfully.

If you are getting an error, in order to install the same versions as me, go to the venv\Scripts directory from the current directory and run the venv virtual environment with the stdutd environment open with the activate command. Then, copy the utdrequirements.txt file in the stable-diffusion-webui-1.4.0-venv folder in this github project to the venv\Scripts folder, install the requirements with the "pip install -r requirements.txt" command and re-run the webui-user.bat file. This will help solve your problem. This way, you will have installed the same versions as me. Remember that your Cuda version and the Cuda versions in our library must be compatible with your graphics card.

If stable diffusion is turned on successfully, set COMMANDLINE_ARGS=--xformers" line to "COMMANDLINE_ARGS=--xformers --skip-install" for faster startup on subsequent startups.



### Sample Lora Training and Usage Video

Will be uploaded soon...

# Stable Diffusion WebUi ve Kohya Basit Kurulum Rehberi

Bu projede birbiriyle uyumlu şekilde çalışan "AUTOMATIC1111 stable diffusion webui" projesi ile "Kohya" projesinin kurulumunu anlatacağız.

# Türkçe Rehber

### Anaconda Kurulum
Anaconda'yı aşağıdaki bağlantıdan yükleyin
https://www.anaconda.com/download


### Visual Studio C++ Kütüphanelerini Yükleyin
https://visualstudio.microsoft.com/tr/downloads/

adresinden visual studioyu indirip kurun.
Windows ortam değişkenlerinizdeki path bölümüne

"C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\VC\Tools\MSVC\14.37.32822\bin\Hostx64\x86\"
dizinini ekleyin.

(Dizin içerisinde cl.exe'nin bulunduğuna dikkat edin!)

Eğer sizdeki versiyon farklı ise Microsoft Visual Studio dizininde iken cl.exe dosyasını aratın ve çıkan dosyalardaki cl.exe'nin mevcut olduğu dizini kopyalayıp path olarak ortam değişkenlerine ekleyin.
Kurulumu doğru yapıp yapmadığınızı anlamak için cmd açıp "cl" komutunu yazın. Dönen çıktı mevcut ise cl.exe'yi başarılı bir şekilde kurmuşsunuz demektir.


### ENV Dosyalarını Kurun
Bu projedeki /conda-envs/ klasöründeki tüm yml dosyalarını conda prompt'ta aşağıdaki komutlar ile kurun. Bu komutları girmeden önce anaconda prompt üzerinde /conda-envs/ dizininde olduğunuza dikkat edin. 

"conda env create -f kohya.yml"

"conda env create -f stddataset.yml"

"conda env create -f stdutd.yml"


### Kohya Kurulumu
https://github.com/bmaltais/kohya_ss/releases/tag/v22.6.0

bağlantısından kohya dosyalarını indirip kuracağınız dizine çıkartın. Tavsiyem tüm bu rehberde yer alan kurulumlar için C dizininde bir ai klasörü oluşturmanızdır.


"conda activate kohya"

komutu ile anaconda prompt üzerinde kohya sanal ortamını aktifleştirin.

Kohya'yı zipten çıkardığınız dizine gidin.

Kohya sanal ortamındayken komut satırına setup.bat yazıp komutu çalıştırın.

Kurulurken size seçenekler sunacak. Yerel bilgisayarınıza kuracağınızı seçin ve geri kalan tüm sorulara no yanıtını verin. FP16 ya da BF16 sorusunda ekran kartınız yeterli ise FP16 seçip devam edin. Son soruya ise all cevabını verip kurulumu tamamlayın. Aslında tüm bu adımlar varsayılan kurulum ayarlarıdır.

Kurulumun başarılı olup olmadığını kontrol etmek için gui.bat dosyasını kohya sanal ortamında anaconda prompt üzerinde çalıştırın.
Eğer http://127.0.0.1:7860/ yayında ise başarılı bir şekilde kurulmuş demektir.

Eğer hata alıyorsanız benimle aynı sürümleri kurabilmek adına mevcut dizinden venv\Scripts dizinine gidip activate komutu ile venv sanal ortamını kohya ortamı açıkken çalıştırın. Ardından bu github projemde yer alan kohya_ss-22.6.0-venv klasöründeki utdrequirements.txt dosyasını venv\Scripts klasörüne kopyalayıp "pip install -r requirements.txt" komutu ile gereklilikleri yükleyin ve gui.bat dosyasını yeniden çalıştırın. Bu sorununuzu çözmeye yardımcı olacaktır. Böylece benimle aynı sürümleri kurmuş olacaksınız. Unutmayın ki Cuda versiyonunuz ve kütüphanemizde yer alan Cuda versiyonları sizin ekran kartınızla uyumlu olmalıdır.

Bitsandbytes hatası alıyorsanız yine venv ortamı aktifken pip install bitsandbytes komutu ile yükleme yapmalısınız.


### Stable Diffusion kurulumu
https://github.com/AUTOMATIC1111/stable-diffusion-webui/releases/tag/v1.4.0

bağlantısından Stable Diffusion dosyalarını indirip kuracağınız dizine çıkartın. Tavsiyem tüm bu rehberde yer alan kurulumlar için C dizininde bir ai klasörü oluşturmanızdır.


"conda activate stdutd"

komutu ile stdutd sanal ortamını aktifleştirin.


Stable Diffusion'ı zipten çıkardığınız dizine gidin.

Sanal ortamda iken komut satırına setup.bat yazıp komutu çalıştırın.

webui-user.bat dosyasını not defteri ile açın ve set "COMMANDLINE_ARGS=" satırını "set COMMANDLINE_ARGS=--xformers" ile değiştirin ve bat dosyasını sanal ortam açıkken Anaconda Prompt üzerinde çalıştırın.

Ardından kendisi kuruluma başlayacaktır.


Kurulum sırasında "v1-5-pruned-emaonly" modelinin indirilmesinde sorun yaşıyorsanız "https://huggingface.co/runwayml/stable-diffusion-v1-5/blob/main/v1-5-pruned-emaonly.safetensors" bağlantısından modeli indirip "models\Stable-diffusion" klasörüne yükleyin ve kurulumu yeniden başlatın. Sorun çözülmüş olacaktır.

Eğer http://127.0.0.1:7860/ yayında ise başarılı bir şekilde kurulmuş demektir.

Eğer hata alıyorsanız benimle aynı sürümleri kurabilmek adına mevcut dizinden venv\Scripts dizinine gidip activate komutu ile venv sanal ortamını stdutd ortamı açıkken çalıştırın. Ardından bu github projemde yer alan stable-diffusion-webui-1.4.0-venv klasöründeki utdrequirements.txt dosyasını venv\Scripts klasörüne kopyalayıp "pip install -r requirements.txt" komutu ile gereklilikleri yükleyin ve webui-user.bat dosyasını yeniden çalıştırın. Bu sorununuzu çözmeye yardımcı olacaktır. Böylece benimle aynı sürümleri kurmuş olacaksınız. Unutmayın ki Cuda versiyonunuz ve kütüphanemizde yer alan Cuda versiyonları sizin ekran kartınızla uyumlu olmalıdır.

Eğer stable diffusion başarılı bir şekilde açılırsa bir sonraki başlatmalarda daha hızlı başlangıç için "set COMMANDLINE_ARGS=--xformers" satırını "set COMMANDLINE_ARGS=--xformers --skip-install" olarak değiştirin.


### Örnek Lora Eğitimi ve Kullanım Videosu

Yakında yüklenecek...


