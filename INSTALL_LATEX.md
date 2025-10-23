# 📦 Instalação do LaTeX para Compilar o Paper

## ❌ Erro Detectado

```
make: pdflatex: No such file or directory
```

**Causa**: LaTeX não está instalado no sistema.

---

## ✅ Soluções

### Opção 1: Instalar LaTeX Completo (Recomendado)

```bash
# Ubuntu/Debian
sudo apt-get update
sudo apt-get install texlive-full

# Ou versão básica (mais rápida)
sudo apt-get install texlive-latex-base texlive-latex-extra texlive-bibtex-extra
```

**Tamanho**: 
- `texlive-full`: ~5 GB (tudo incluído)
- `texlive-latex-base + extras`: ~500 MB (suficiente)

**Tempo de instalação**: 10-30 minutos (depende da conexão)

---

### Opção 2: Usar Overleaf (Online, Sem Instalação)

**Vantagens**:
- ✅ Sem instalação local
- ✅ Colaboração online
- ✅ Compilação automática
- ✅ Controle de versão

**Passos**:

1. Acesse: https://www.overleaf.com
2. Crie conta gratuita
3. New Project → Upload Project
4. Compacte a pasta Paper_MUSCAT:
   ```bash
   cd /home/suporte/Pesquisas/UTM_Sensors
   zip -r Paper_MUSCAT.zip Paper_MUSCAT/
   ```
5. Upload do ZIP no Overleaf
6. Compile online!

---

### Opção 3: Visualizar o Conteúdo (Sem Compilar)

Enquanto não compila, você pode ler o conteúdo:

```bash
cd /home/suporte/Pesquisas/UTM_Sensors/Paper_MUSCAT

# Ver todas as seções
cat sections/*.tex | less

# Ou seção por seção
cat sections/01_introduction.tex
cat sections/02_related_work.tex
# etc...
```

---

## 🚀 Instalação Rápida (Recomendada)

### Para Ubuntu/Debian:

```bash
# Instalação mínima (suficiente para o paper)
sudo apt-get update
sudo apt-get install -y texlive-latex-base \
                        texlive-latex-extra \
                        texlive-fonts-recommended \
                        texlive-fonts-extra \
                        texlive-bibtex-extra

# Testar instalação
pdflatex --version

# Compilar o paper
cd /home/suporte/Pesquisas/UTM_Sensors/Paper_MUSCAT
make
```

---

## 📄 Alternativa: Criar PDF Manualmente

Se não quiser instalar LaTeX completo, você pode:

### 1. Usar Docker (se tiver)

```bash
docker run --rm -v $(pwd):/workspace -w /workspace \
  texlive/texlive:latest \
  pdflatex main.tex
```

### 2. Copiar para Overleaf

**Mais simples** para quem não quer instalar localmente:

```bash
cd /home/suporte/Pesquisas/UTM_Sensors
zip -r Paper_MUSCAT.zip Paper_MUSCAT/
```

Depois upload em https://www.overleaf.com

---

## ✅ Checklist de Instalação

- [ ] LaTeX instalado (`pdflatex --version` funciona)
- [ ] BibTeX instalado (`bibtex --version` funciona)
- [ ] Figuras acessíveis
- [ ] Paper compila sem erros (`make`)
- [ ] PDF gerado (`main.pdf` existe)

---

## 🐛 Troubleshooting

### Erro: "Package X not found"
```bash
# Instalar pacotes adicionais
sudo apt-get install texlive-latex-extra texlive-fonts-extra
```

### Erro: "Bibliography not found"
```bash
# Verificar arquivo existe
ls references/references.bib

# Compilar manualmente
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

### Erro: "Figure not found"
```bash
# Verificar links
ls -la figures/
# Recriar links se necessário
```

---

## 📊 Tamanhos de Instalação

| Opção | Tamanho | Tempo | Recomendação |
|-------|---------|-------|--------------|
| `texlive-full` | ~5 GB | 30 min | ✅ Se tem espaço |
| `texlive-latex-base + extras` | ~500 MB | 10 min | ✅ Suficiente |
| **Overleaf online** | 0 MB | 0 min | ✅✅ Mais fácil |
| Docker | ~300 MB | 5 min | Para quem já usa Docker |

---

## 🎯 Recomendação

**Para começar rápido**: Use **Overleaf** (opção 2)
- Sem instalação
- Compila online
- Colaboração fácil

**Para trabalho local**: Instale `texlive-latex-base + extras`
- Suficiente para o paper
- Não muito pesado (~500 MB)

---

## 📝 Próximos Passos

1. **Escolher opção** (Overleaf ou instalação local)
2. **Compilar o paper**
3. **Ver o PDF gerado**
4. **Revisar e refinar**

---

**Recomendação**: Use Overleaf para facilitar! 🚀

