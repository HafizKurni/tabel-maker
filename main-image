import streamlit as st

# --- Translations ---
translations = {
    'EN': {
        'page_title': "HTML Table Maker",
        'app_title': "📝 HTML Table Maker for Google Sites",
        'welcome_message': """
Welcome! This tool helps you create a clean, styled HTML table without writing any code.
1.  **Configure** the table settings in the sidebar on the left.
2.  **Enter** your data in the grid below.
3.  **To add an image**, check "Enable Image URLs" in the sidebar and paste the image link directly into a cell.
4.  **Copy** the generated HTML code at the bottom.
""",
        'config_header': "⚙️ Table Configuration",
        'cols_label': "Number of Columns",
        'rows_label': "Number of Rows (including header)",
        'style_header': "🎨 Styling Options",
        'header_bg_color': "Header Background Color",
        'odd_row_color': "Odd Row Background Color",
        'even_row_color': "Even Row Background Color",
        'border_color': "Border Color",
        'text_color': "Text Color",
        'table_width': "Table Width (%)",
        'font_family': "Font Family",
        'enable_images': "Enable Image URLs",
        'image_width': "Max Image Width (px)",
        'data_entry_header': "✏️ Step 2: Enter Your Data",
        'header_input_label': "Header {c}",
        'preview_header': "👀 Step 3: Preview and Copy Code",
        'live_preview_subheader': "Live Table Preview",
        'copy_code_subheader': "Copy HTML Code",
        'success_message': "You can now copy the code above and embed it in your Google Site!",
        'default_header_text': "Header {c}",
        'default_cell_text': "Cell {r}-{c}"
    },
    'ID': {
        'page_title': "Pembuat Tabel HTML",
        'app_title': "📝 Pembuat Tabel HTML untuk Google Sites",
        'welcome_message': """
Selamat datang! Alat ini membantu Anda membuat tabel HTML yang bersih dan bergaya tanpa menulis kode.
1.  **Konfigurasi** pengaturan tabel di bilah sisi kiri.
2.  **Masukkan** data Anda pada kolom di bawah.
3.  **Untuk menambah gambar**, centang "Aktifkan URL Gambar" di sidebar dan tempel tautan gambar langsung ke dalam sel.
4.  **Salin** kode HTML yang dihasilkan di bagian bawah.
""",
        'config_header': "⚙️ Konfigurasi Tabel",
        'cols_label': "Jumlah Kolom",
        'rows_label': "Jumlah Baris (termasuk header)",
        'style_header': "🎨 Opsi Gaya",
        'header_bg_color': "Warna Latar Header",
        'odd_row_color': "Warna Latar Baris Ganjil",
        'even_row_color': "Warna Latar Baris Genap",
        'border_color': "Warna Garis Batas",
        'text_color': "Warna Teks",
        'table_width': "Lebar Tabel (%)",
        'font_family': "Jenis Huruf",
        'enable_images': "Aktifkan URL Gambar",
        'image_width': "Lebar Maksimal Gambar (px)",
        'data_entry_header': "✏️ Langkah 2: Masukkan Data Anda",
        'header_input_label': "Header {c}",
        'preview_header': "👀 Langkah 3: Pratinjau dan Salin Kode",
        'live_preview_subheader': "Pratinjau Tabel Langsung",
        'copy_code_subheader': "Salin Kode HTML",
        'success_message': "Anda sekarang dapat menyalin kode di atas dan menanamkannya di Google Site Anda!",
        'default_header_text': "Header {c}",
        'default_cell_text': "Sel {r}-{c}"
    }
}

# --- Sidebar for Configuration ---
with st.sidebar:
    language = st.radio("Language / Bahasa", ('EN', 'ID'), horizontal=True)
    T = translations[language] # Select the right translation dictionary
    st.header(T['config_header'])
    
    # Grid dimensions
    col_count = st.number_input(T['cols_label'], min_value=1, value=3, step=1)
    row_count = st.number_input(T['rows_label'], min_value=2, value=4, step=1)
    
    st.markdown("---")
    
    # Styling options
    st.subheader(T['style_header'])
    header_color = st.color_picker(T['header_bg_color'], "#f2f2f2")
    odd_row_color = st.color_picker(T['odd_row_color'], "#ffffff")
    even_row_color = st.color_picker(T['even_row_color'], "#f9f9f9")
    border_color = st.color_picker(T['border_color'], "#dddddd")
    text_color = st.color_picker(T['text_color'], "#000000")
    table_width = st.slider(T['table_width'], min_value=10, max_value=100, value=100)
    font_family = st.selectbox(
        T['font_family'],
        options=["sans-serif", "Arial", "Helvetica", "Verdana", "serif", "Times New Roman", "Georgia", "monospace", "Courier New"],
        index=0
    )
    st.markdown("---")
    # Image options
    enable_images = st.checkbox(T['enable_images'], value=True)
    image_max_width = 100
    if enable_images:
        image_max_width = st.number_input(T['image_width'], min_value=10, max_value=500, value=100)


# --- Page Configuration ---
st.set_page_config(
    page_title=T['page_title'],
    page_icon="📝",
    layout="wide"
)

# --- App Title and Description ---
st.title(T['app_title'])
st.markdown(T['welcome_message'])


# --- State Management for Table Data ---
# Initialize or update the data grid in session state
if 'table_data' not in st.session_state:
    st.session_state.table_data = [[f"Data {r+1}-{c+1}" for c in range(col_count)] for r in range(row_count)]

# Adjust table_data if dimensions change
current_rows = len(st.session_state.table_data)
current_cols = len(st.session_state.table_data[0])

if current_rows != row_count or current_cols != col_count:
    new_data = [[f"" for _ in range(col_count)] for _ in range(row_count)]
    for r in range(min(current_rows, row_count)):
        for c in range(min(current_cols, col_count)):
            new_data[r][c] = st.session_state.table_data[r][c]
    st.session_state.table_data = new_data
    # Set default text for new cells
    for r in range(row_count):
        for c in range(col_count):
            if not st.session_state.table_data[r][c]:
                 if r == 0:
                     st.session_state.table_data[r][c] = T['default_header_text'].format(c=c+1)
                 else:
                     st.session_state.table_data[r][c] = T['default_cell_text'].format(r=r, c=c+1)


# --- Main Area for Data Entry ---
st.header(T['data_entry_header'])

# Create a container for the input grid
grid_container = st.container()

with grid_container:
    # Create columns for the header row
    header_cols = st.columns(col_count)
    for c in range(col_count):
        with header_cols[c]:
            st.session_state.table_data[0][c] = st.text_input(
                label=T['header_input_label'].format(c=c+1),
                value=st.session_state.table_data[0][c],
                key=f"header_{c}"
            )

    st.markdown("---")
    
    # Create columns for the data rows
    for r in range(1, row_count):
        row_cols = st.columns(col_count)
        for c in range(col_count):
            with row_cols[c]:
                 st.session_state.table_data[r][c] = st.text_input(
                    label=f"Row {r}, Col {c+1}",
                    value=st.session_state.table_data[r][c],
                    key=f"cell_{r}_{c}",
                    label_visibility="collapsed" # Hides the label to keep it clean
                )

# --- HTML Generation Logic ---
def get_cell_content(text_content):
    """Checks if text is an image URL and returns either an <img> tag or plain text."""
    if enable_images and text_content.startswith(('http://', 'https://')) and text_content.lower().endswith(('.png', '.jpg', '.jpeg', '.gif', '.svg', '.webp')):
        return f'<img src="{text_content}" alt="Gambar dari pengguna" style="max-width:{image_max_width}px; height:auto; display: block; margin-left: auto; margin-right: auto;">'
    return text_content

def generate_html_code():
    """Generates the HTML string based on session state data and styles."""
    
    html = [
        '',
        f'<table style="width:{table_width}%; border-collapse: collapse; font-family: {font_family};">'
    ]

    # Table Header (thead)
    html.append(f'  <thead style="background-color: {header_color};">')
    html.append('    <tr>')
    for c in range(col_count):
        header_text = st.session_state.table_data[0][c]
        content = get_cell_content(header_text)
        html.append(f'      <th style="border: 1px solid {border_color}; text-align: left; padding: 12px; color: {text_color}; vertical-align: middle;">{content}</th>')
    html.append('    </tr>')
    html.append('  </thead>')

    # Table Body (tbody)
    html.append('  <tbody>')
    for r in range(1, row_count):
        # Determine row color for alternating pattern
        row_index_in_body = r - 1
        bg_color = odd_row_color if row_index_in_body % 2 == 0 else even_row_color
        
        html.append(f'    <tr style="background-color: {bg_color};">')
        for c in range(col_count):
            cell_text = st.session_state.table_data[r][c]
            content = get_cell_content(cell_text)
            html.append(f'      <td style="border: 1px solid {border_color}; text-align: left; padding: 8px; color: {text_color}; vertical-align: middle;">{content}</td>')
        html.append('    </tr>')
    html.append('  </tbody>')
    
    # End of table
    html.append('</table>')
    
    return "\n".join(html)

final_html_code = generate_html_code()

# --- Display Preview and Final Code ---
st.markdown("---")
st.header(T['preview_header'])

# Live Preview
st.subheader(T['live_preview_subheader'])
st.markdown(final_html_code, unsafe_allow_html=True)

# Generated Code
st.subheader(T['copy_code_subheader'])
st.code(final_html_code, language='html')

st.success(T['success_message'])
